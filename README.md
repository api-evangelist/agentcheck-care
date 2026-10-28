# AgentCheck

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

AgentCheck is an AI-agent diagnostic service at agentcheck.care: give it the URL of a bot - an A2A agent or an OpenAI-compatible chat endpoint - and it runs synthetic-persona conversations, OWASP LLM Top 10 prompt-injection tests, PII-leakage scans, hallucination, over-refusal, bias and brand-alignment checks across ten modules, then delivers a scored report by magic link. A free scan needs no login; paid one-off tiers (Quick Check $10, Full Check $25, Deep Check $75) are bought through Stripe Checkout. The service is published as a 35-operation FastAPI OpenAPI 3.1.0 contract with Swagger UI and ReDoc, a machine-readable tier catalog and live free-scan quota endpoint, and is itself a conformant A2A 0.3.0 agent with two skills (free-scan, paid-checkup) served from the same host.

**Areas:** AI Agents · AI Safety · Security Testing · Prompt Injection · LLM Evaluation · A2A · Agent-Native · Chatbots · Compliance · Developer Tools

## AgentCheck on APIs.io

Everything profiled for AgentCheck is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/agentcheck-care/](https://apis.io/providers/agentcheck-care/)** — or go straight to one of the APIs or properties below.

### APIs (20)

- [AgentCheck A2A Agent](https://apis.io/apis/agentcheck-care/agentcheck-a2a-agent/) — Agent2Agent (A2A 0.3.0) surface of the same service - a conformant agent card at /.well-known/agent-card.json declaring two text/plain skills, free-scan and…
- [AgentCheck A2a API](https://apis.io/apis/agentcheck-care/agentcheck-care-a2a-api/) — The A2a API from AgentCheck — 1 operation(s) for a2a.
- [AgentCheck Agent Checkup API](https://apis.io/apis/agentcheck-care/agentcheck-care-agentcheckup-api/) — The AgentCheckup API from AgentCheck — 1 operation(s) for agentcheckup.
- [AgentCheck Checkout API](https://apis.io/apis/agentcheck-care/agentcheck-care-checkout-api/) — The Checkout API from AgentCheck — 4 operation(s) for checkout.
- [AgentCheck Checkup API](https://apis.io/apis/agentcheck-care/agentcheck-care-checkup-api/) — The Checkup API from AgentCheck — 5 operation(s) for checkup.
- [AgentCheck Credits API](https://apis.io/apis/agentcheck-care/agentcheck-care-credits-api/) — The Credits API from AgentCheck — 1 operation(s) for credits.
- [AgentCheck Exam API](https://apis.io/apis/agentcheck-care/agentcheck-care-exam-api/) — The Exam API from AgentCheck — 4 operation(s) for exam.
- [AgentCheck Free Scan Status API](https://apis.io/apis/agentcheck-care/agentcheck-care-free-scan-status-api/) — The Free Scan Status API from AgentCheck — 1 operation(s) for free scan status.
- [AgentCheck Free Scans API](https://apis.io/apis/agentcheck-care/agentcheck-care-free-scans-api/) — The Free Scans API from AgentCheck — 1 operation(s) for free scans.
- [AgentCheck Health API](https://apis.io/apis/agentcheck-care/agentcheck-care-health-api/) — The Health API from AgentCheck — 1 operation(s) for health.
- [AgentCheck Privacy API](https://apis.io/apis/agentcheck-care/agentcheck-care-privacy-api/) — The Privacy API from AgentCheck — 1 operation(s) for privacy.
- [AgentCheck Report API](https://apis.io/apis/agentcheck-care/agentcheck-care-report-api/) — The Report API from AgentCheck — 1 operation(s) for report.
- [AgentCheck Robots.txt API](https://apis.io/apis/agentcheck-care/agentcheck-care-robots-txt-api/) — The Robots.txt API from AgentCheck — 1 operation(s) for robots.txt.
- [AgentCheck Sitemap.xml API](https://apis.io/apis/agentcheck-care/agentcheck-care-sitemap-xml-api/) — The Sitemap.xml API from AgentCheck — 1 operation(s) for sitemap.xml.
- [AgentCheck Stats API](https://apis.io/apis/agentcheck-care/agentcheck-care-stats-api/) — The Stats API from AgentCheck — 2 operation(s) for stats.
- [AgentCheck Stripe Webhook API](https://apis.io/apis/agentcheck-care/agentcheck-care-stripe-webhook-api/) — The Stripe Webhook API from AgentCheck — 2 operation(s) for stripe webhook.
- [AgentCheck Terms API](https://apis.io/apis/agentcheck-care/agentcheck-care-terms-api/) — The Terms API from AgentCheck — 1 operation(s) for terms.
- [AgentCheck Tiers API](https://apis.io/apis/agentcheck-care/agentcheck-care-tiers-api/) — The Tiers API from AgentCheck — 1 operation(s) for tiers.
- [AgentCheck Validate Bot API](https://apis.io/apis/agentcheck-care/agentcheck-care-validate-bot-api/) — The Validate Bot API from AgentCheck — 2 operation(s) for validate bot.
- [AgentCheck .well Known API](https://apis.io/apis/agentcheck-care/agentcheck-care-well-known-api/) — The .well Known API from AgentCheck — 1 operation(s) for .well known.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [agentcheck](https://apis.io/servers/agentcheck-care/agentcheck/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Agentcheck Care Openapi Overlay](https://apis.io/overlays/agentcheck-care/agentcheck-care-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Agentcheck Care Authentication](https://apis.io/security/agentcheck-care/agentcheck-care-authentication/)
- [Agentcheck Care Domain Security](https://apis.io/security/agentcheck-care/agentcheck-care-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Agentcheck Care Plans Pricing](https://apis.io/plans/agentcheck-care/agentcheck-care-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Agentcheck Care Rate Limits](https://apis.io/rate-limits/agentcheck-care/agentcheck-care-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://agentcheck.care/)
- [Documentation](https://agentcheck.care/docs)
- [API reference](https://agentcheck.care/redoc)
- [Pricing](https://agentcheck.care/#pricing)
- [Terms of service](https://agentcheck.care/terms)
- [Privacy policy](https://agentcheck.care/privacy)

## API Evangelist rating

**Kin Score 41.6** — developing · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 37.8 |
| Contract governance | 18.2 |
| Operational transparency | 21.1 |
| Developer ergonomics | 35.1 |
| Access clarity | 57.9 |

**Agent readiness 32.1** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 32.4** — AI & Biometrics

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/agentcheck-care/](https://apis.io/providers/agentcheck-care/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for AgentCheck: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/agentcheck-care/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
