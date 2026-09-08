# AKA incident lessons — sanitized design input
Status: Reported history plus reviewed source excerpts; not a current production audit

Sources: founder-supplied AKA CONNECT System Incident and Defect Review (July–August 2026); supplied HTML and backend excerpts; recovery-test outputs in the planning conversation. Raw customer data and report attachments intentionally excluded.

| Failure class | Preventive requirement |
|---|---|
| Stale browser replaced newer records | Server-side atomic concurrency, record-level transactions; client merges are insufficient. |
| Duplicate references/payments | Database uniqueness, atomic sequences, idempotent submissions; business duplicate review. |
| Blind approval deleted linked revisions | Consequence preview and dependency-aware, authorized archival/correction. |
| Upload overflow and silent save failure | Separate file storage, verified uploads, truthful save status. |
| Invoice edits overwritten by quote edits | Document ownership and controlled version propagation. |
| Client-only/store-only access control | Record/field/action authorization across all endpoints. |
| Mutable audit history | Server-generated events and enforceable append-only protections. |
| Raw user fields and unsafe templates | Dedicated account services, safe projections and contextual output handling. |
| Patches broke unrelated screens | Modules, integration tests, browser smoke tests and staging. |
| Expired sessions retried forever | Authentication-aware bounded retry policy. |
| Warning dismissals reappeared | Stable rule/record finding identifiers. |
| Backups shared the production server | Independent encrypted recovery copies and tested restoration. |

## Evidence caveats
The report's closed statuses are not accepted blindly: inspected handlers checked versions separately from writes, permitted omitted versions and used whole-array writes in item endpoints. The excerpts also showed bypasses around user protections. Reported mitigation does not prove complete resolution.

Missing-measurement totals in the report require reconciliation; the unresolved deletion preview, historical duplicates, visibility complaints and conflicting delivery terms require explicit owners and business decisions. Do not silently normalize source contradictions during migration.

## Recovery progress (historical snapshot, 2026-09-08)
Operator outputs showed successful encryption, off-site upload/download checksum checks, full decryption and isolated PostgreSQL restoration with readable collections. Attachment completeness/full application recovery remain unverified. Restored audit history was unusually small and needs investigation. The test container was stopped, not removed. Off-site automation is not installed or scheduled; a separate local draft is awaiting review. Do not interpret this snapshot as a current backup-health signal.
