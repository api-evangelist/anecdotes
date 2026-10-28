# anecdotes

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

anecdotes is an enterprise Governance, Risk and Compliance (GRC) platform, founded in 2020 and headquartered in Tel Aviv, that pairs a GRC data engine with AI agents to replace point-in-time audit cycles with continuous, evidence-backed compliance. Its Compliance OS collects evidence automatically from 230+ pre-built plugins into 1,000+ predefined artifacts, maps that evidence across 60+ frameworks at once, and drives core applications for controls, requirements, risk, policy management, findings and user access review. Developers reach the platform through a documented REST API at api.anecdotes.ai (API key exchanged for a short-lived JWT), a hosted MCP Proxy at mcp.anecdotes.ai that exposes GRC domains as agent tools, a FedRAMP 20x Trust Center API with genuinely public endpoints, SAML SSO and SCIM provisioning, and outbound event webhooks driven by Playbooks.

**Areas:** Company · Compliance · Governance · Risk Management · Security · GRC · Audit · Evidence · Continuous Compliance · FedRAMP · Artificial Intelligence · Agents

## anecdotes on APIs.io

Everything profiled for anecdotes is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/anecdotes/](https://apis.io/providers/anecdotes/)** — or go straight to one of the APIs or properties below.

### APIs (18)

- [Anecdotes MCP Proxy](https://apis.io/apis/anecdotes/anecdotes-mcp-proxy/) — A hosted Model Context Protocol proxy that exposes Anecdotes GRC domains - risk, control, evidence, policy, framework, uar, analysis, comments, requirement…
- [anecdotes Analysis Rules API](https://apis.io/apis/anecdotes/anecdotes-analysis-rules-api/) — **Analysis rules** evaluate evidence table rows for **gaps or warnings**; configure query, scoping, and alert levels, and read **execution results** per…
- [anecdotes Authorization API](https://apis.io/apis/anecdotes/anecdotes-authorization-api/) — API key to JWT exchange and token management.
- [anecdotes Create Controls API](https://apis.io/apis/anecdotes/anecdotes-create-controls-api/) — Create one or more **custom controls** in a framework.
- [anecdotes Create Evidence API](https://apis.io/apis/anecdotes/anecdotes-create-evidence-api/) — Create custom **Evidence Collections**, **attach** JSON/CSV files to a collection, and upload **manual** evidence of any type. Customer-pushed evidence can…
- [anecdotes Custom Fields API](https://apis.io/apis/anecdotes/anecdotes-custom-fields-api/) — **Custom fields** extend platform resources (including **requirements**) with your own **dropdown**, **multi-select**, or **free-text** values. These…
- [anecdotes Download Evidence API](https://apis.io/apis/anecdotes/anecdotes-download-evidence-api/) — Download **raw** evidence payloads, processed **evidence tables**, combined full-or-raw streams, and latest binary payloads.
- [anecdotes Findings API](https://apis.io/apis/anecdotes/anecdotes-findings-api/) — **Findings** record compliance gaps and issues, including links to controls, evidence, and policies.
- [anecdotes Framework API](https://apis.io/apis/anecdotes/anecdotes-framework-api/) — A **framework** in anecdotes is a compliance program built from a formally written standard or regulation (e.g. ISO/IEC 27001, SOC 2, HIPAA, CSA STAR). It…
- [anecdotes Gated API](https://apis.io/apis/anecdotes/anecdotes-gated-api/) — Authorization package, KSI and evidence endpoints. Require an approved FedRAMP user JWT.
- [anecdotes Policy Manager API](https://apis.io/apis/anecdotes/anecdotes-policy-manager-api/) — **Policy Manager** allows you to create, edit, and manage policies for your organization. List customer-owned policies, library templates, policy versions,…
- [anecdotes Public API](https://apis.io/apis/anecdotes/anecdotes-public-api/) — Public Trust Center information. No authentication required.
- [anecdotes Read Controls API](https://apis.io/apis/anecdotes/anecdotes-read-controls-api/) — List all controls or fetch by framework or id.
- [anecdotes Read Evidence Metadata API](https://apis.io/apis/anecdotes/anecdotes-read-evidence-metadata-api/) — List and retrieve **evidence definitions**, **instance metadata**, and multi-instance **run history**.
- [anecdotes Requirements API](https://apis.io/apis/anecdotes/anecdotes-requirements-api/) — **Requirements** tie **controls** to expected **evidence** and framework scoping. These endpoints cover listing customer requirements, simple **create /…
- [anecdotes Risk API](https://apis.io/apis/anecdotes/anecdotes-risk-api/) — **Risks** live in **risk registers** in Risk Manager: inherent/residual dimensions, treatment, custom fields, and links to evidence. **API:** create, list…
- [anecdotes Token API](https://apis.io/apis/anecdotes/anecdotes-token-api/) — Exchange your **API key** for a **short-lived JWT** (1 hour). Send the JWT as `Authorization: Bearer <token>` on all subsequent requests.
- [anecdotes Update Control Metadata API](https://apis.io/apis/anecdotes/anecdotes-update-control-metadata-api/) — Update or delete a **custom control**'s name, description, category, and implementation.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Anecdotes Playbooks Webhooks](https://apis.io/asyncapis/anecdotes/anecdotes-playbooks-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [anecdotes](https://apis.io/servers/anecdotes/anecdotes/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Anecdotes Agentic Access](https://apis.io/agentic-access/anecdotes/anecdotes-agentic-access/)

#### Collections (4)

Postman and Open Collection request collections.

- [Anecdotes FedRAMP 20x Trust Center API](https://apis.io/collections/anecdotes/open-anecdotes-fedramp-20x/)
- [Anecdotes API](https://apis.io/collections/anecdotes/open-anecdotes-grc/)
- [Anecdotes API](https://apis.io/collections/anecdotes/open-anecdotes-grc-openapi-original/)
- [FedRAMP 20x API](https://apis.io/collections/anecdotes/postman-anecdotes-fedramp-20x/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Anecdotes Grc Overlay](https://apis.io/overlays/anecdotes/anecdotes-grc-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Anecdotes Authentication](https://apis.io/security/anecdotes/anecdotes-authentication/)
- [Anecdotes Domain Security](https://apis.io/security/anecdotes/anecdotes-domain-security/)
- [Anecdotes Trust Center](https://apis.io/security/anecdotes/anecdotes-trust-center/)
- [Anecdotes Vulnerability Disclosure](https://apis.io/security/anecdotes/anecdotes-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Anecdotes Plans Pricing](https://apis.io/plans/anecdotes/anecdotes-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Anecdotes Rate Limits](https://apis.io/rate-limits/anecdotes/anecdotes-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.anecdotes.ai/)
- [Documentation](https://help.anecdotes.ai/)
- [Getting started](https://help.anecdotes.ai/technical-setup/api/using-the-anecdotes-api)
- [API reference](https://help.anecdotes.ai/api/overview)
- [Pricing](https://www.anecdotes.ai/pricing)
- [Sign up](https://www.anecdotes.ai/get-started)
- [Support](https://help.anecdotes.ai/)
- [Blog](https://www.anecdotes.ai/blog)
- [Security](https://www.anecdotes.ai/trust)
- [Compliance](https://www.anecdotes.ai/trust)
- [Terms of service](https://www.anecdotes.ai/terms-of-use)
- [Privacy policy](https://www.anecdotes.ai/privacy-policy)
- [GitHub](https://github.com/anecdotes-ai)
- [Status](https://status.anecdotes.ai/)

## API Evangelist rating

**Kin Score 67.8** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 64.7 |
| Contract governance | 18.2 |
| Operational transparency | 73.7 |
| Developer ergonomics | 70.4 |
| Access clarity | 81.6 |

**Agent readiness 36.8** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 32.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/anecdotes/](https://apis.io/providers/anecdotes/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for anecdotes: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/anecdotes/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
