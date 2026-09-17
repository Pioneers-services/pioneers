# Decision register
Baseline: 2026-09-08. Source: Shaheen's explicit planning discussion.

| ID | Status | Decision |
|---|---|---|
| D-001 | Agreed | Pioneers is the commercial company; pioneers.services is the customer-facing domain. |
| D-002 | Agreed | Carminta is the proprietary orchestrator/AI engineer behind products, not the ERP. |
| D-003 | Agreed | ERP name is Connect X1 — by Carminta; embedded implementation assistant is Carminta X1. |
| D-004 | Agreed | Rebuild as SaaS from scratch; use AKA as concept/layout/workflow reference, not architecture. |
| D-005 | Agreed | Commercial industry-specific customers first; quality and accessible price; MENA then Africa, USA, global ambition. |
| D-006 | Agreed | Scanning/Action Center and approved configuration are central. |
| D-007 | Agreed | New modules require Pioneers engineering/review; memory and learning do not imply uncontrolled code changes. |
| D-008 | Agreed | Shaheen has final authority; AI CEO Assistant supports company-wide planning, coordination and verification. |
| D-009 | Approved action | Initialize this private repository as the Pioneers planning area. No production changes included. |
| D-010 | Proposed | Modular monolith, managed PostgreSQL/object storage, TypeScript stack and replaceable model APIs. |
| D-011 | Open | Hosting providers, regions, billing provider, application budget and final launch scope. |
| D-012 | Operational constraint | Backup storage budget is free-only for now; scheduling remains incomplete. |
| D-013 | Agreed | First real pilot customer: AKA Homes, 21 users. An additional customer is expected to have at least 15 users; this is a planning assumption, not a subscription minimum. Concurrent usage is not yet established. |
| D-014 | Mandatory requirement | Connect X1 must have multi-tenant SaaS architecture from day one, even while only AKA is live. Tenant isolation, configuration-based onboarding, subscription entitlements and separate environments are foundational; no company-specific code forks. Implementation and isolation must be verified before a second real tenant is onboarded. |
| D-015 | Open | AKA incident lessons: the unresolved deletion-preview gap (blind approval could delete linked revisions without a consequence preview) needs an explicit owner and business decision before migration; see engineering/aka-incident-lessons.md. |
| D-016 | Open | AKA incident lessons: historical duplicate records (duplicate references/payments from the prior system) need an explicit owner and business decision on reconciliation before migration; see engineering/aka-incident-lessons.md. |
| D-017 | Open | AKA incident lessons: reported customer visibility complaints from the prior system need an explicit owner and business decision; see engineering/aka-incident-lessons.md. |
| D-018 | Open | AKA incident lessons: conflicting delivery terms recorded in the prior system need an explicit owner and business decision on which terms are authoritative; see engineering/aka-incident-lessons.md. |

Record amendments with rationale and approval; do not silently rewrite historical decisions. Detailed technical standards and sequencing remain proposals until reviewed.
