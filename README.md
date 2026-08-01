# anecdotes

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
