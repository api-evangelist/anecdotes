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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

anecdotes is an enterprise Governance, Risk and Compliance (GRC) platform, founded in 2020 and
headquartered in Tel Aviv, that pairs a GRC data engine with AI agents to replace point-in-time audit
cycles with continuous, evidence-backed compliance. Its Compliance OS collects evidence automatically
from 230+ pre-built plugins into 1,000+ predefined artifacts, maps that evidence across 60+ frameworks
at once, and drives applications for controls, requirements, risk, policy management, findings and user
access review.

- Website: https://www.anecdotes.ai/
- Documentation: https://help.anecdotes.ai/
- API reference: https://help.anecdotes.ai/api/overview
- Status: https://status.anecdotes.ai/
- Trust center: https://trust.anecdotes.ai/

## APIs

| API | Base URL | Contract |
|---|---|---|
| Anecdotes GRC API | https://api.anecdotes.ai | `openapi/anecdotes-grc-openapi.yml` (53 operations) |
| Anecdotes FedRAMP 20x Trust Center API | https://api.anecdotes.ai | `openapi/anecdotes-fedramp-20x-openapi.yml` (8 operations) |
| Anecdotes MCP Proxy | https://mcp.anecdotes.ai | `mcp/anecdotes-mcp.yml` (10 domains, 14 tools) |

Authentication is two-step: an API token created in the platform is exchanged at
`GET /identity/v1/apikey/exchange` for a JWT valid for one hour, sent as a bearer token thereafter.
A descriptive `User-Agent` header is mandatory. The FedRAMP 20x public tier requires no credentials.
