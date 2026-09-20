---
name: agentcheck-paid-checkup
description: Choose a paid AgentCheck tier from the live catalog, create a Stripe Checkout session, and retrieve the report after payment, respecting the published refund and retry rules.
api: AgentCheck Checkup API
base_url: https://agentcheck.care
operations:
  - get_tiers_api_tiers_get
  - create_checkout_api_checkout_post
  - upgrade_checkout_api_checkout_get
  - stream_progress_api_checkup__checkup_id__stream_get
  - get_report_api_checkup__checkup_id__report_get
auth: none (payment is completed by a human in Stripe Checkout)
generated: '2026-09-19'
method: generated
source: openapi/_original/agentcheck-care-openapi.json; https://agentcheck.care/api/tiers; https://agentcheck.care/terms
---

# Buy and run a paid checkup

This flow spends real money. An agent should surface the price and the refund rule to the human before creating the checkout, and must hand the Stripe URL to a human — there is no API path to complete payment.

## Steps

1. **Read the tiers** — `GET /api/tiers` (`get_tiers_api_tiers_get`). Use the live ids and prices rather than hard-coding them: observed on 2026-09-19 as `basic` Quick Check $10, `full` Full Check $25, `enterprise` Deep Check $75 (plans/agentcheck-care-plans-pricing.yml).
2. **Create the checkout** — `POST /api/checkout` (`create_checkout_api_checkout_post`) with a `CheckoutRequest`: `tier` (one of the ids above; default is `basic`), `bot_type`, `bot_url`, and the optional context fields (`system_prompt`, `website_url`, `email`, owner-perception fields). The response is the Stripe Checkout redirect URL. Give it to the human. There is no idempotency key — do not retry a POST whose response you did not read; check with the human whether a checkout already exists.
3. **Or upgrade a free scan** — if a free checkup already ran, `GET /api/checkout?tier=<id>&checkup_id=<id>` (`upgrade_checkout_api_checkout_get`) reuses the stored bot details and 302s to Stripe.
4. **After payment** Stripe redirects to `/api/checkout/success`, which launches the run. Follow it with `GET /api/checkup/{checkup_id}/stream` (`stream_progress_api_checkup__checkup_id__stream_get`) and fetch `GET /api/checkup/{checkup_id}/report` (`get_report_api_checkup__checkup_id__report_get`) when it completes.

## Rules the human must know before paying

- **Refunds** (terms 3.3): full refund only if the checkup fails because of AgentCheck's own error; no refund for a low score. Refunds are requested by email — there is no API operation and no stated window (conventions/ reversibility: documented).
- **Unreachable bot** (terms 3.4): AgentCheck tries for 5 minutes; if it cannot connect, the same payment can be retried because the checkup id stays valid. In exam mode, `POST /exam/{token}/relaunch` recreates an expired paid session with the same parameters.
- A "Deep Check" report is not a compliance certification (terms 5.4), whatever the tier is marketed for.
- Prices may change; the price at purchase time is the one charged (terms 3.2).
