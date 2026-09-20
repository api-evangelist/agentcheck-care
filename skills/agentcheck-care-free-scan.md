---
name: agentcheck-free-scan
description: Check free-scan quota, validate a target bot, start a free AgentCheck checkup, follow progress over SSE, and fetch the scored report.
api: AgentCheck Checkup API
base_url: https://agentcheck.care
operations:
  - free_scans_endpoint_api_free_scans_get
  - validate_bot_api_validate_bot_post
  - start_checkup_api_checkup_post
  - stream_progress_api_checkup__checkup_id__stream_get
  - get_report_api_checkup__checkup_id__report_get
auth: none
generated: '2026-09-19'
method: generated
source: openapi/_original/agentcheck-care-openapi.json; https://agentcheck.care/terms; https://agentcheck.care/privacy
---

# Run a free AgentCheck scan

Only test a bot you own or are authorised to test (terms 2.1). Free scans are a shared, limited resource, so check the pool before spending one.

## Steps

1. **Check quota** — `GET /api/free-scans` (`free_scans_endpoint_api_free_scans_get`). Read `remaining` and `reset_in_seconds`. If `remaining` is 0, stop; the pool is 30 per week for everyone and 2 per week per user (terms 3.1), and the exhaustion status code is undocumented.
2. **Validate the target** — `POST /api/validate-bot` (`validate_bot_api_validate_bot_post`) with the bot URL. This confirms the URL is safe and answers as an A2A agent or an OpenAI-compatible chat API without starting a checkup. The request schema is not declared in the spec; the home page form sends the bot URL and type.
3. **Start the checkup** — `POST /api/checkup` (`start_checkup_api_checkup_post`) with a `CheckupRequest`: `bot_type` (`"a2a"` default, or chat API), `bot_url`, `tier: "free"`, and optionally `system_prompt`, `bot_description`, `industry`, `sample_questions`, `website_url`, `email`. Do NOT retry a timed-out POST blindly — there is no idempotency key and a retry starts a second checkup and burns a second free-scan unit (see conventions/).
4. **Follow progress** — `GET /api/checkup/{checkup_id}/stream` (`stream_progress_api_checkup__checkup_id__stream_get`) is a server-sent-events stream. AgentCheck will keep trying to reach the bot for up to 5 minutes before failing the run (terms 3.4).
5. **Fetch the report** — `GET /api/checkup/{checkup_id}/report` (`get_report_api_checkup__checkup_id__report_get`). A 404 `{"detail":"Checkup not found"}` means the run has not persisted yet. The human-readable report lives at `/report/{checkup_id}?token=...` — treat that magic link as a password (privacy 3.1).

## Rules

- If you pass the customer's own `api_key` (their bot's chat-API key) it is held in memory for the session only (privacy 1.3); prefer a temporary key with a spending cap (terms 2.2).
- Errors are FastAPI-shaped `{"detail": ...}`; 422 carries an array naming the bad field (errors/agentcheck-care-problem-types.yml).
- Call the slash-less path; `/api/checkup/` is a duplicate of the same handler.
- No status page exists; `GET /api/health` is the only liveness signal.
