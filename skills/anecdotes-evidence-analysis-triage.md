---
name: Triage compliance gaps from evidence analysis
description: Read analysis rules and their results, find where evidence shows a compliance gap, and open or update the corresponding finding.
api: openapi/anecdotes-grc-openapi.yml
operations: [exchangeApiKey, getAnalysisRules, getAnalysisRulesResults, getEvidence, getEvidenceFullData, listFindings, createFinding, getFindingById, patchFinding]
generated: '2026-07-31'
method: generated
source: https://help.anecdotes.ai/api/analysis-rules
---

# Triage compliance gaps from evidence analysis

Analysis rules are what turn collected evidence into a pass or fail. This flow reads their results
and turns failures into findings.

## Prerequisites

Authenticate first (see `anecdotes-authenticate.md`). Needs **Admin** to write findings.

## Steps

1. **List the rules.** Call `getAnalysisRules` — `GET /analysis-rules/v1/analysis-rules` — filtering
   with `rule_type` and `rule_state` so you only look at active rules of the kind you care about.

2. **Read the results.** Call `getAnalysisRulesResults` —
   `GET /analysis-rules/v1/analysis-rules/rule_results_by_filter`. Results carry `evidence_id`,
   `parent_evidence_id`, `evidence_instance_id` and `service_instance_id`, plus an alert level.

3. **Get the underlying data when a rule fails.** Call `getEvidence` for metadata and
   `getEvidenceFullData` — `GET /evidence/v1/evidence/{evidence_instance_id}/full_data` — for the
   processed table the platform itself shows. This is what a human will want to see in the ticket.

4. **Check for an existing finding first.** Call `listFindings` — `GET /compliance/v1/findings` — before
   creating anything.

5. **Open or update the finding.** `createFinding` — `POST /compliance/v1/findings` — for a new gap;
   `patchFinding` — `PATCH /compliance/v1/findings/{finding_id}` — to update one that already exists.
   Read back with `getFindingById`.

## Rules

- **Always check step 4 before step 5.** Nothing de-duplicates findings for you.
- **Alert level is the triage signal.** Use the rule's alert level rather than treating every failing
  result as equally urgent.
- **Do not delete to "reset".** `deleteFindings` removes audit history. Patch the status instead.
- **Evidence instances are versioned.** A result points at a specific `evidence_instance_id`. When you
  quote data in a finding, quote the instance you evaluated, not the latest — they drift apart.
- **Prefer the event to the poll.** A Playbook can trigger on "Compliance gap detected in evidence" and
  POST to your webhook, which is cheaper than polling this flow. See
  `asyncapi/anecdotes-playbooks-webhooks.yml`.
