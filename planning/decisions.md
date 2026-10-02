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

## D-021 — Connect X1 first industry: interiors and fit-out (2026-10-01, approved by Shaheen)
- Connect X1's first market is the interiors value chain: architects, interior designers, fit-out contractors, joinery/carpentry workshops and furniture/fit-out factories. Replaces the 2026-09-25 "SMBs, no single vertical" direction.
- Projects are the product core: brief → design stages → drawings/revisions → quotation with revisions and client approval → measurements → workshop/factory production → site → handover → snagging/warranty; suppliers, per-project materials/costing, accounting and Bahrain VAT underneath.
- Pilots: AKA Homes (21 users) and a Bahrain interior design studio (8–10 users, ~20 live projects, needs suppliers + accounting, ~2-month window). Everything is built by Pioneers; no third-party ERP/accounting products.
- Go-live must include the NBR VAT return (boxes 1–17), matching the audited competitor InventERP; projects, quotation revisions/approvals and Carminta X1 are the differentiators.

## D-022 — Pioneers Add-on Store (decided 2026-09-25, recorded 2026-10-01, approved by Shaheen)
- Every Pioneers feature, module and add-on (e.g. Connect X1 modules M1–M23 and add-ons A1–A15) is listed separately on its own page of the Pioneers website store.
- Not an open marketplace: Pioneers is the only provider across every package and does the activation per project/tenant; each add-on carries its own fee.
- Prices are set later in the pricing system. Source: founder decision in the 2026-09-25 strategy session; Product Strategy & Roadmap doc, decisions table.

## D-023 — Connect X1 catalog: inclusions and commerce connectors (2026-10-01, approved by Shaheen)
- Carminta X1 (catalog M22) is included in every Connect X1 subscription, not sold as a separate module. The earlier "Carminta X1 metered by user type" direction (2026-09-25) is superseded unless Shaheen restates it for the subscription tiers.
- The country tax pack (catalog A1, e.g. Bahrain VAT with the NBR return boxes 1–17) is included.
- Commerce: the **Shopify connector is active** and is the e-commerce path for now. The **Connect X1 Storefront is prepared as a product and listed in the Add-on Store (D-022) but deactivated** until it is ready.
- **Website integration** (Pioneers-built websites ↔ Connect X1, e.g. enquiries/forms into CRM, catalogue and orders where relevant) is an active connector.

## D-024 — Connect X1 structure, Carminta-led setup and the Owner role (2026-10-01, approved by Shaheen)
**Structure.** Customers choose **features on screen**; underneath, features stay grouped into 9 areas used for dependencies, testing and pricing tiers:
1 Sales (leads, enquiries, quotations, orders, payment allocation, contracts & variations) · 2 Projects (design pipeline, initial/final measurements, handover) · 3 Pricing system (cutlist costing, pricing dashboard) · 4 Operations (delivery teams, vehicles, site supervisors, warranty) · 5 Financial system (accounting, invoicing, expenses, signatures, reports, project costing; built with its own boundary so it can become a separate product later) · 6 Inventory (purchasing, suppliers, subcontractors, products, stock) · 7 HR (employees, appraisal, performance, timesheets, payroll) · 8 Production pipeline · 9 Core platform & Carminta X1 (Action Center, activity log, library, notifications, analysis, reports, access control, intelligent dashboard, hierarchy) — included for every tenant.
Each shared record has one owning area (e.g. invoices → Finance; the cutlist → one record used by Projects, Pricing and Production); visibility everywhere else is set by role permissions. When a feature needs others, the system adds them automatically and Carminta explains why. The five industry packages (architecture practice, interior design studio, fit-out contractor, joinery workshop, furniture & fit-out factory) are the starting presets.

**Journey.** (1) No registration to explore: anyone can choose a package and features, and ask Carminta about any feature — she answers from product knowledge only, with no customer data. (2) Registration starts at payment; the Owner account is created. (3) The customer chooses their country; Carminta proposes currency, tax pack, fiscal year and language for it; the owner approves. (4) Branding: logo, colours/theme, live preview on screens and PDFs. (5) Documents (old quotations, price/product lists, org chart, Excel) are uploaded only after registration; Carminta reads them and proposes imports, a quotation template and a hierarchy draft. (6) Hierarchy: company → branches → departments → teams → roles → users; features placed on departments; approval chains. (7) Connections (Shopify, website, WhatsApp, bank) attached to the features that use them. (8) Carminta's final check → owner approves → go live. Every step is versioned and reversible until go-live.

**Carminta in setup.** She proposes, the owner approves; she never applies changes alone. Uploaded documents stay in that tenant and go only to AI providers that don't train on or retain customer data; instructions embedded in uploaded files are ignored.

**Owner role.** Sees everything in their own company only; at least one owner always (ownership is transferred, never left empty); two-factor login required; every owner action is logged; approvals still apply; decides who else sees salaries/payroll. Pioneers support is never an owner — separate, time-limited, logged access.

**Timeline.** Wave 1 grows to about 10 weeks (option A): Carminta as setup builder, document reading and branding move into Wave 1; Carminta's daily project-watching stays in Wave 2.

## D-025 — Connect X1 hosting: AWS, Bahrain home region (2026-10-02, approved by Shaheen)
- **Stack and hosting:** the NestJS (TypeScript) server, workers and Carminta X1 run as containers on AWS ECS Fargate (ARM); PostgreSQL on Amazon RDS. Home region **Bahrain `me-south-1`**; backup copies go to **UAE `me-central-1`**, so data and backups stay in the Gulf. Kept from the hosting audit: React screens on Vercel Pro, files on Cloudflare R2, off-site backups on Backblaze B2. The AI provider choice is not part of this decision.
- **Basis:** vendor price lists and docs, checked 2026-10-02 (`projects/connect-x1/hosting-test-results.md`). Shaheen skipped the week-1 hosting test. Latency figures are estimates and get measured during the build.
- **Start lean, grow with customers** (on-demand prices):
  - pilot about $73/month (1 container, load balancer, RDS db.t4g.micro single-AZ with 7-day point-in-time restore);
  - before go-live, a second container (about +$19) and a Multi-AZ standby (about +$17);
  - about $560–660/month at 500 users online at once.
  - The account has $120 of AWS credit.
- **Cost guardrails:**
  - budget alerts ($20, $50);
  - Cost Anomaly Detection;
  - fixed scaling ceilings, no NAT gateway, 14-day log retention;
  - every resource tagged;
  - no root use.
  - Each new resource is created only after Shaheen approves an itemised cost list.
- **Rejected:**
  - Supabase Pro in Mumbai: no failover standby on Pro, point-in-time restore is a $100/month add-on, and it means two vendors.
  - DigitalOcean: cheapest with a standby, but no Gulf region, and from 15 Oct 2026 a standby needs Advanced Edition.
  - US East, Frankfurt and Mumbai: 5–19% cheaper but farther from, and outside, the launch countries.
- **Launch countries:** Bahrain, Egypt, KSA, UAE, Oman and Kuwait. AWS has no live KSA region. A tenant that must stay in-country uses dedicated hosting (catalog A14) in an approved location. Each country's data-protection rules get a legal review before customers there are signed.
