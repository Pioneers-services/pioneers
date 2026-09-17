# Architecture proposal
Status: Proposed, providers and stack not approved

## Starting shape
Modular monolith with clear business boundaries; React/TypeScript interface and TypeScript backend are candidates. Managed PostgreSQL for transactional records, private object storage for files, durable workers for scanning/imports/reports/notifications. Established authentication, transactional email, monitoring, and subscription entitlements.

Supabase is a candidate for database/auth/storage, not a requirement or the AI runtime. Keep the existing backup-only project separate from future application environments. Model-provider APIs sit behind a Pioneers-owned adapter. No dedicated GPU fleet, Kubernetes, or microservice-per-module requirement at launch.

## Correctness and isolation
Tenant identity comes from verified membership. Enforce tenant, record, action and field permissions across APIs, files, search, cache, jobs, WebSockets and AI retrieval. Database constraints reinforce authorization and integrity. Store records as rows; use atomic version checks, transactions, idempotency keys and unique reference constraints. Financial calculations use explicit decimal/rounding rules, never model arithmetic. Content and permission locking must be implemented as an explicit allowlist of what is permitted, never a denylist of forbidden keywords or patterns — a denylist can only enumerate the wording someone has already thought of, and anything phrased differently slips through. The pioneers-site-local CMS carried exactly this defect: a keyword-regex lock let disclosure content become editable because its wording did not match any denylist trigger, exposing 86 legal/operational fields on a live page. It was fixed by inverting the check to a positive per-section allowlist, so any field is locked by default unless its section is explicitly listed as safe. The same allowlist-first rule applies to every authorization boundary in Connect X1: tenant, record, action and field permissions.

## Performance
Paginate and index; load screen-specific data; keep attachments out of record payloads; move slow work to workers. Measure latency, queue delays and query costs; set capacity targets after pilot workload discovery. Ordinary operations must work during AI-provider outages.

## Pricing and analysis
Version effective price lists, dimensions/units, costs, overhead, margin/markup, tax, discount limits and rounding. Snapshot quotation calculations; do not rewrite issued documents after catalog changes. Define metrics centrally with drill-down evidence. Actual margin requires actual cost capture.

## Country and languages
Arabic/English and RTL/LTR foundations; choose additional languages by actual African markets. Separate UI translation from document localization and legal compliance. Country rule packs need sources, effective dates, review, versioning, and regression tests. Bahrain is a proposed pilot based on AKA; legal entity, registrations and hosting requirements remain to be confirmed.

## Delivery environments
Separate development, staging and production credentials/data. No real charges or customer messages from staging. Test migration on copies, reconcile records and attachment references, define cutover and rollback. Avoid concurrent independent financial writes in old and new systems.
