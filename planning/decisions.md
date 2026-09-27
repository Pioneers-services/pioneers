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
| D-010 | Agreed (2026-09-18) | Modular monolith, managed PostgreSQL/object storage, TypeScript stack and replaceable model APIs. Direction approved; this covers architecture shape only, not a specific vendor selection or spend commitment. |
| D-011 | Partially agreed (2026-09-18) | Hosting provider for pioneers.services: a Hostinger VPS the founder already holds. Region, billing/renewal terms and monthly budget figure are still not recorded — do not treat this as a completed decision or provision Connect X1/Carminta X1/Servio X3 infrastructure against it until those are set. |
| D-012 | Operational constraint | Backup storage budget is free-only for now; scheduling remains incomplete. |
| D-013 | Agreed | First real pilot customer: AKA Homes, 21 users. An additional customer is expected to have at least 15 users; this is a planning assumption, not a subscription minimum. Concurrent usage is not yet established. |
| D-014 | Mandatory requirement | Connect X1 must have multi-tenant SaaS architecture from day one, even while only AKA is live. Tenant isolation, configuration-based onboarding, subscription entitlements and separate environments are foundational; no company-specific code forks. Implementation and isolation must be verified before a second real tenant is onboarded. |
| D-015 | Open | AKA incident lessons: the unresolved deletion-preview gap (blind approval could delete linked revisions without a consequence preview) needs an explicit owner and business decision before migration; see engineering/aka-incident-lessons.md. |
| D-016 | Open | AKA incident lessons: historical duplicate records (duplicate references/payments from the prior system) need an explicit owner and business decision on reconciliation before migration; see engineering/aka-incident-lessons.md. |
| D-017 | Open | AKA incident lessons: reported customer visibility complaints from the prior system need an explicit owner and business decision; see engineering/aka-incident-lessons.md. |
| D-018 | Open | AKA incident lessons: conflicting delivery terms recorded in the prior system need an explicit owner and business decision on which terms are authoritative; see engineering/aka-incident-lessons.md. |
| D-019 | Agreed (2026-09-18) | pioneers.services is the commercial/marketing website only (the pioneers-site-local vertical slice: public pages, consultation leads, admin CMS). Carminta X1, Connect X1 and Servio X3 are separate products worked on later; their multi-tenant SaaS requirement (D-014) applies to those products, not to the marketing website. |

Record amendments with rationale and approval; do not silently rewrite historical decisions. Detailed technical standards and sequencing remain proposals until reviewed.

## D-015 — Product family and naming (2026-09-10, approved by Shaheen)
- Carminta is Pioneers Services' PRIVATE orchestrator; never sold separately.
- Each product carries one daughter agent: **Connect X1 → Carminta X1**, **Servio X3 → Carminta X3**. No public "grandchild" layer.
- Product names always carry their generation suffix (Connect X1, Servio X3).
- All products are served under pioneers.services; no separate product domains.
- Pioneers brand identity, trademark direction and fonts: approved. Carminta emblem: rework pending (keep lower signal element; replace upper part).

## D-016 — Governance per project (2026-09-10)
Each project keeps its own folder under projects/ with decisions.md and open-questions.md. Company-wide decisions stay in planning/decisions.md.

## D-017 — Website & operations platform direction (2026-09-10)
- Website languages: Arabic + English now; French next stage.
- Approved first delivery: public site + minimal lead inbox. Include chatbot-led consultation, social links and consent-based source tracking. Quotations/proforma/invoices and CMS remain requested follow-on scope; exact phase order is proposed, not approved.
- Pioneers will use Connect X1 for its ERP. Reusing its modules for the website dashboard is a proposal; minimal lead inbox first is approved. No numeric tenant ID or shared runtime architecture is approved.
- Chat: chatbot first; escalates to human consultation request. Two staff members answer/follow up.
- Social: LinkedIn, Instagram, Facebook, X, TikTok — outbound links + source tracking only; no DM integration.
- Analytics: self-hosted, consent-based, no third-party data sharing.
- Email: Hostinger Starter Business Email. Mailbox activation pending; confirm original suppost@pioneers.services versus suggested support@pioneers.services before provisioning.
- Hosting preference: same VPS as AKA, with separate application credentials, database, network and storage plus resource limits. Containers share the host kernel, resources and failure domain: total isolation is not possible. Docker installation and production deployment remain pending explicit approval.
- Invoicing entity: Egypt (registration + VAT/tax number to be supplied); currency follows customer origin.

## D-020 — Visual architecture map before building (2026-09-27, approved by Shaheen)
- Every new project and every engineering-architecture change gets a visual map (actors, components and hosting, labelled data flows, trust boundaries, ownership, phases, unknowns) before build starts.
- The map is checked against real sources (code/config, vendor docs, decisions, client confirmation); anything unsourced is drawn as an unknown and logged in open-questions.md.
- One map per project at `projects/<project>/architecture-map.html`, kept current with a "last verified" date.
- Encoded as the Carminta skill `architecture-visual-map` (carminta/skills/, Claude skills format); Claude uses the same skill as Carminta's instructor.
