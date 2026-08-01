---
name: Export framework and control posture
description: Pull the current compliance posture for a framework — its controls, their statuses and the requirements behind them — for an auditor, a dashboard or a downstream system.
api: openapi/anecdotes-grc-openapi.yml
operations: [exchangeApiKey, getFrameworks, getControlsByFramework, getControlsByIds, listRequirements, getRequirementById, exportFramework]
generated: '2026-07-31'
method: generated
source: https://help.anecdotes.ai/api/framework
---

# Export framework and control posture

The most common read flow: report the state of a compliance program to someone outside Anecdotes.

## Prerequisites

Authenticate first (see `anecdotes-authenticate.md`). The **Auditor** role is sufficient for this
flow, and is the right choice when the consumer is an external auditor.

## Steps

1. **List frameworks.** Call `getFrameworks` — `GET /api/v1/framework` — to find the framework id.
   Anecdotes maps one body of evidence across many frameworks, so expect several (SOC 2, ISO 27001,
   custom frameworks) sharing the same underlying controls.

2. **Pull the controls for that framework.** Call `getControlsByFramework` —
   `GET /controls/control/framework/{framework_id}`. Each control carries a `control_status`. If you
   only need specific controls, `getControlsByIds` — `POST /controls/control/read` — takes a body of
   ids and is one round trip instead of many.

3. **Pull the requirements.** Call `listRequirements` — `GET /api/v1/requirement` — paginating with
   `limit` and `offset`. Use `getRequirementById` for detail on a single one. Controls carry
   `control_requirement_ids` and `linked_requirements`, which is how the two sides join.

4. **Or take the whole thing at once.** `exportFramework` —
   `GET /api/v1/framework/{framework_id}/download` — returns the framework as a downloadable export.
   Prefer this when the consumer wants a document rather than a live feed.

## Rules

- **Paginate with `limit` and `offset`.** There is no cursor. Keep pulling until a page comes back
  short.
- **Understand the hierarchy before mapping.** Framework → Control → Requirement, with Evidence
  attached and Analysis Rules evaluating it. See `data-model/anecdotes-data-model.yml`.
- **Control status is derived, not authoritative on its own.** Statuses can be changed automatically by
  evidence analysis and can be frozen by an auto-downgrade playbook. Report the status and the
  as-of time together.
- **A 403 on a read means the Auditor token has no access to that framework.** It does not mean the
  framework is missing.
