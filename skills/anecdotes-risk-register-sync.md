---
name: Sync a risk register with Anecdotes
description: Create, read and update risks in an Anecdotes risk register from an external system of record.
api: openapi/anecdotes-grc-openapi.yml
operations: [exchangeApiKey, createRisk, getRisks, getRisk, updateRisk]
generated: '2026-07-31'
method: generated
source: https://help.anecdotes.ai/api/risk
---

# Sync a risk register with Anecdotes

Use this when a risk register lives somewhere else — a GRC spreadsheet, a ServiceNow table, an
internal app — and Anecdotes needs to reflect it.

## Prerequisites

Authenticate first (see `anecdotes-authenticate.md`). Requires the **Admin** role, since this writes.

## Steps

1. **Read what is already there.** Call `getRisks` — `GET /risk/v1/risk/full`. Filter with `risk_ids`
   for a targeted read, and set `exclude_review` when you do not want risks currently under review in
   the result. Build a map from your external id to the Anecdotes risk id before writing anything.

2. **Create what is missing.** Call `createRisk` — `POST /risk/v1/risk`.

3. **Update what has drifted.** Call `updateRisk` — `PATCH /risk/v1/risk/{risk_id}` — with only the
   fields that changed. Read a single risk back with `getRisk` — `GET /risk/v1/risk/{risk_id}` — to
   confirm.

## Rules

- **Match before you create.** There is no idempotency key and no upsert. Running this flow twice
  without the id map in step 1 will create duplicate risks.
- **Registers are separate namespaces.** Since May 2026 risks live in multiple registers, each with its
  own fields, structure, settings and risk appetite. A risk id is meaningful only within its register —
  do not assume one global list.
- **Respect risk appetite enforcement.** A register can be configured to block accepting risks above its
  appetite without approval. A write that violates that will be rejected; surface the rejection rather
  than retrying.
- **PATCH is partial.** Send only changed fields. Sending the whole object will overwrite fields other
  people edited in the UI.
- **Bulk import is a UI flow, not an API one.** For a large first-time load, the platform's in-app CSV
  import against a register-specific template is the supported path.
