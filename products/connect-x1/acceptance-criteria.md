# Acceptance criteria
Status: Proposed release gates; none marked implemented

| ID | Required proof |
|---|---|
| AC-01 | A second company can onboard without code edits; cross-company API, file, search, job and live-update access is denied. |
| AC-02 | Concurrent writes cannot silently remove payments or overwrite a newer record. Missing/stale versions fail explicitly. |
| AC-03 | Retrying a payment request does not duplicate it; suspected business duplicates require confirmation. |
| AC-04 | Concurrent document numbering is unique in its defined scope. Historical corrections remain traceable. |
| AC-05 | Rejected writes never display Saved; incomplete files cannot satisfy required-document milestones. |
| AC-06 | Deletion/voiding previews dependencies and consequences, checks approvals, and preserves required financial history. |
| AC-07 | Server audit events cannot be edited by ordinary application users; security against privileged actors has an explicit threat model. |
| AC-08 | Price changes do not rewrite approved quotes; invoice/quote ownership and revision rules are explicit. |
| AC-09 | Action Center findings have stable IDs, evidence, owner, rule version and post-action verification; dismissal is not resolution. |
| AC-10 | Carminta cannot bypass permissions; previews identify affected records; partial failures are visible and retries safe. |
| AC-11 | Backup restoration recovers database and expected files in an isolated environment; alarms detect failures. |
| AC-12 | Arabic/English forms and generated documents preserve amounts, direction, formatting and business terminology. |
| AC-13 | One complete pilot job works through sales/design/production/handover; financial totals reconcile to agreed source records. |
| AC-14 | Core product remains usable when the AI provider is unavailable. |

For every gate: attach test command, environment, result, limitations and reviewer. Passing unit tests alone does not prove a full production workflow.
