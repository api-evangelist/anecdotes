---
name: Authenticate against the Anecdotes API
description: Exchange an Anecdotes API token for a short-lived JWT and make an authenticated call, handling the mandatory User-Agent and the 60-minute expiry.
api: openapi/anecdotes-grc-openapi.yml
operations: [exchangeApiKey, getFrameworks]
generated: '2026-07-31'
method: generated
source: https://help.anecdotes.ai/technical-setup/api/using-the-anecdotes-api
---

# Authenticate against the Anecdotes API

Every other Anecdotes skill depends on this one. Anecdotes uses a two-step model: a long-lived API
token created in the platform is exchanged for a JWT that lives for one hour.

## Before you start

The API token is created by a human in the platform under **Administration → API tokens**, with a
name, an expiration date, and a role. You cannot create one over the API. Pick the least-privileged
role that works:

- `Auditor` — read and export the frameworks the auditor can see.
- `Integrator` — create evidence and push data into self-managed evidence.
- `Admin` — everything, including the MCP Proxy.

## Steps

1. **Exchange the token.** Call `exchangeApiKey` — `GET /identity/v1/apikey/exchange` on
   `https://api.anecdotes.ai` — with the token in the `x-anecdotes-api-key` header. The response is the
   JWT as `text/plain`, not JSON. Do not try to parse it as an object.

2. **Set both required headers on every subsequent call.**
   - `Authorization: Bearer <JWT>`
   - `User-Agent: your-app-name/1.0 (+contact@domain.com)`

   The User-Agent is not optional. A request with a valid JWT and no acceptable User-Agent is the
   documented cause of a `403`, and the message will not tell you that is why.

3. **Verify.** Call `getFrameworks` — `GET /api/v1/framework` — and confirm a 200.

## Rules

- **Re-exchange on 401, do not retry.** The JWT expires after 60 minutes. A `401` means "get a new
  JWT", not "the credentials are wrong". Retrying the same JWT will fail forever.
- **A 403 is about role or User-Agent, not expiry.** Check the token's role first, then the User-Agent.
- **There is no refresh token and no OAuth.** Do not look for an authorize/token endpoint or scopes;
  authorization is entirely by the token's role.
- **Cache the JWT** for its lifetime rather than exchanging on every call — the API signals rate limits
  through `x-rate-limit-limit`, `x-rate-limit-remaining` and `x-rate-limit-reset` headers.
- **No idempotency keys exist.** Write operations carry no de-duplication contract, so never blind-retry
  a POST/PATCH/PUT after a timeout — read back first to see whether it landed.
