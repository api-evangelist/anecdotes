---
name: Read the Anecdotes FedRAMP 20x trust package
description: Pull Anecdotes' own compliance posture — public CSO metadata with no credentials, then the gated authorization package, KSIs and evidence after access approval.
api: openapi/anecdotes-fedramp-20x-openapi.yml
operations: [getPublicInfo, requestFedrampAccess, exchangeApiKeyFedramp, listFedrampTokens, getAuthorizationPackage, getKsi, getFedrampEvidence, getFedrampEvidenceHistory]
generated: '2026-07-31'
method: generated
source: https://help.anecdotes.ai/technical-setup/fedramp-20x-trust-center-and-api
---

# Read the Anecdotes FedRAMP 20x trust package

This API is how Anecdotes exposes its *own* compliance posture. It has a genuinely public tier, which
is rare — start there before asking anyone for access.

## Steps

### Public tier — no credentials at all

1. Call `getPublicInfo` — `GET /fedramp20x/v1/public/info?evidence_id={code}` — with the header
   `trustcenterurl: trust.anecdotes.ai`. No token is needed. Useful codes:

   - `builder_2795822335733` — offering public information (service model, deployment model, contacts)
   - `builder_2639056738947` — detailed service list with impact levels
   - `builder_2666397450893` — status page uptime rollup
   - `builder_2110205339759` — Recommended Secure Configuration index
   - `url_2037408219127` — the Trust Center URL
   - `manual_2454242086620` — the API documentation (`.docx`)
   - `manual_2578511430147` — the Postman collection (`.json`)

2. Set `Accept` to match what you want: `application/json` or `text/csv` for structured codes,
   `application/octet-stream` for the two `manual_*` document codes.

### Gated tier — approval required

3. Call `requestFedrampAccess` — `POST /fedramp20x/v1/access` — with `first_name`, `last_name`,
   `email`, `company` (set to `FedRAMP`) and `job_title`. Approved users receive credentials by email.
   The response tells you which state you landed in via `access_pending`, `user_exists` and
   `user_denied_or_revoked`.

4. Once approved, exchange your key with `exchangeApiKeyFedramp` — `GET /identity/v1/apikey/exchange` —
   and use the JWT as a bearer token. `listFedrampTokens` shows your active tokens.

5. Call `getAuthorizationPackage` — `GET /fedramp20x/v1/authorization-package` — with
   `include_evidence_ids=true` for the full posture, then `getKsi` —
   `GET /fedramp20x/v1/ksi/{ksi_code}` (for example `FRR-IAM-01`) — for a specific Key Security
   Indicator.

6. Pull the proof with `getFedrampEvidence` and `getFedrampEvidenceHistory`.

## Rules

- **`trustcenterurl` is required on every FedRAMP call**, including the public ones.
- **`company` must be `FedRAMP`** on the access request — the provider states this explicitly.
- **Content type drives the response, not the path.** The same endpoint returns JSON, CSV, PDF or a
  binary download depending on `Accept`. The authorization package and KSI endpoints support
  `application/pdf`.
- **Paginate the gated reads.** Evidence uses `page` (1-indexed) and `page_size` (max 1000); history
  uses `limit` (default 100, max 10000) with optional `from_date`/`to_date`.
- **Pin an evidence `version`** when you need a stable citation. Omitting it returns the latest, which
  will move under you.
