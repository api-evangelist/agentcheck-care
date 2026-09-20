---
name: agentcheck-a2a-request
description: Reach AgentCheck over the Agent2Agent protocol - read the agent card, send a message/send request for a free scan or a paid checkup, and handle the payment-link reply.
api: AgentCheck A2A Agent
base_url: https://agentcheck.care/a2a
operations:
  - agent_card__well_known_agent_card_json_get
  - a2a_endpoint_a2a_post
auth: none (the card declares no securitySchemes and the endpoint accepts anonymous JSON-RPC)
generated: '2026-09-19'
method: generated
source: a2a/agentcheck-care-agent-card.json (fetched 2026-09-19); openapi/_original/agentcheck-care-openapi.json
---

# Ask AgentCheck for a scan over A2A

AgentCheck is itself an A2A agent (protocolVersion 0.3.0, two skills). This is the shortest path for another agent: no REST client, no schema, one JSON-RPC call.

## Steps

1. **Read the card** — `GET https://agentcheck.care/.well-known/agent-card.json` (`agent_card__well_known_agent_card_json_get`). Confirm `url` is `https://agentcheck.care/a2a` and note `capabilities.streaming` is `false` — use `message/send`, not `message/stream`. Input and output modes are `text/plain`.
2. **Free scan** — `POST https://agentcheck.care/a2a` (`a2a_endpoint_a2a_post`) with a JSON-RPC 2.0 `message/send` whose text follows the card's own example: `Run a free scan on https://my-bot.example.com`. The free-scan skill runs 1 persona, 5 injection tests, a PII scan and a system-prompt adherence check.
3. **Paid checkup** — same call with text of the form `Test https://my-bot.example.com with Full Check` (or `Quick Check` / `Deep Check`). The card says the reply is a **payment link to complete before testing begins** — hand that link to a human; do not attempt to pay.
4. **Read the reply as text.** Output mode is `text/plain`; there is no structured result part declared. The scored report will be behind a magic link — treat it as a password.

## Rules

- Only unknown methods were probed by API Evangelist; the endpoint returned a standard JSON-RPC `-32601` for an unsupported method, so expect JSON-RPC error objects rather than HTTP error codes.
- The free-scan pool (30 per week shared, 2 per user) applies here too; `GET /api/free-scans` on the same host tells you whether a free request will be honoured.
- Push notifications and state-transition history are `false` in the card — poll by re-sending, or switch to the REST SSE stream if you have the `checkup_id`.
