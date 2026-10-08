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
- **Stack and hosting:** the NestJS (TypeScript) server, workers and Carminta X1 run as containers on AWS ECS Fargate (ARM); PostgreSQL on Amazon RDS. Home region **Bahrain `me-south-1`**; database backup copies go to **UAE `me-central-1`**, so the database and its backups stay in the Gulf. _Amended 2026-10-02 (team review R22): other data is stored elsewhere: files on Cloudflare R2 (a location hint, not a jurisdiction guarantee), off-site backups on Backblaze B2 (region to be chosen), screens on Vercel, plus the email and AI providers once chosen. A data location matrix will set out each data class._ Kept from the hosting audit: React screens on Vercel Pro, files on Cloudflare R2, off-site backups on Backblaze B2. The AI provider choice is not part of this decision.
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

## D-026 — Connect X1 Wave 1 scope after the Qaflo benchmark; HR as a separable module (2026-10-02, approved by Shaheen)
Benchmark: Qaflo (Dubai), from strategy doc §11. Gaps were logged as Q32–Q40 in `projects/connect-x1/open-questions.md`.
- **Added to Wave 1:**
  - committed cost in project costing (planned vs committed vs actual, margin per project);
  - snag lists and handover;
  - stock on hand vs promised;
  - retention and post-dated cheques, in the Financial system.
- **Workshop tracking** (carpentry, metal, painting, finishing stages) belongs to the Production module (Wave 2), not Projects.
- **HR is a full module, built like the Financial system (D-024):** its own boundary and interfaces, so it can scale or become a separate product later. Bahrain rules (wage protection, LMRA permits, end-of-service gratuity) get checked against official sources when HR is designed.
- **Not now:** GPS site visits (dropped). Samples library and fleet tracking come later (Wave 3 or after).
- **Risk:** Wave 1 grows. If the about-10-week plan slips, accounting reports slip first; tax-invoice correctness never slips (unchanged rule).

## D-027 — Connect X1 pricing model (2026-10-02, approved by Shaheen; first committed as a duplicate D-026, renumbered)
**Structure.** Price = industry package × seat tier. Tiers: Start (5 seats: 1 owner, 1 admin, 3 users), Team (10: 1 owner, 1 admin, 8 managers/users), Business (20: 1 owner, 1 admin, 18), "Call us" for 50+ seats. Roles inside a tier don't change the price; each seat is placed in the hierarchy at implementation and its access set in access control. Workshop/site workers are normal seats (no light user, no workshop stations). Extra seats are sold between tiers; the system moves the customer to the next tier automatically when that is cheaper.

**List prices (BHD/month; Carminta X1 and the home-country tax pack included; shared hosting):**
| Package | Start 5 | Team 10 | Business 20 | Extra seat |
|---|---|---|---|---|
| Architecture practice | 59 | 109 | 209 | 10 |
| Interior design studio | 65 | 119 | 219 | 11 |
| Architecture + Interior design | 75 | 135 | 249 | 12 |
| Fit-out contractor | 69 | 129 | 239 | 12 |
| Joinery workshop | 69 | 129 | 239 | 12 |
| Furniture & fit-out factory | 75 | 139 | 259 | 13 |
Add-ons are priced separately.

**Floor.** No combination of discounts takes the effective price below BHD 9.5 per seat per month; the system caps discounts automatically.

**Carminta X1.** Included with a monthly usage allowance per seat, pooled per company; extra usage is sold in packs. Owner sees usage, warned at 80%; Carminta never stops without warning. Allowance and pack price are set after Carminta's cost is measured in the test bench (working placeholder: 300 requests/seat/month; ~BHD 8 per 1,000 extra).

**Hosting.** Shared (included) or Dedicated by Pioneers on AWS Bahrain (+BHD 75/month for Start/Team, +BHD 120 for Business, custom for Call us; BHD 300 one-time setup). Customer-owned cloud is not offered.

**Implementation fee (one-time).** List: BHD 500 (Start), 1,000 (Team), 1,500 (Business, 20+ seats); Call us quoted. First-year discounted: BHD 350 / 750 / 1,150. Past-transaction import, extra training and custom reports are charged per day.

**Offers and payment.**
- The full list price is always shown first at checkout, then the discount.
- Discounts apply in the first year only; founding price lock for the first year only; the setup fee is never credited back.
- Default payment: two payments, every 6 months, each = (monthly price × 12 + implementation fee) ÷ 2. Example: 95 × 12 + 350 = 1,490 → BHD 745 every 6 months.
- Yearly prepayment: 2 months free (pay 10, get 12), capped by the floor.

## D-028 — Connect X1 billing rules (2026-10-02, approved by Shaheen; amends D-027)
These answer `projects/connect-x1/open-questions.md` Q41–Q47.
- **Seat changes:**
  - No seat or tier changes in the first 6-month period.
  - For the next period, the customer emails customer service at least 2 months before that period starts.
  - The customer is responsible for the number of seats before paying.
  - Billing never moves a customer up or down a tier mid-period. This replaces D-027's automatic tier move.
- **Renewal:** after year 1, renewal is at full list price. The system sends 2 renewal notices in the last 2 months of the term.
- **Carminta X1 allowance:** usage isn't counted for an initial period after implementation, 3, 5 or 7 days depending on the package. Counting starts after that.
- **Currency and invoicing:** the currency follows the country the customer chooses at setup. Pioneers invoices as an Egyptian company.
- **Floor:** lowered from D-027's BHD 9.5 to **BHD 8 per seat per month** in the worst case. This is a startup marketing allowance.
- **Missed payment:**
  - The tenant is locked until the full outstanding balance is paid.
  - A customer who closes the account pays the full (undiscounted) implementation fee, and past periods are recharged at list price with no discount.

## D-029 — Connect X1 as a separate brand with its own website and domain (2026-10-02, approved by Shaheen)
- Connect X1 is totally separate from Pioneers in the market: its own brand, website and domain. This replaces, for Connect X1, D-015's "all products are served under pioneers.services; no separate product domains". D-019 (pioneers.services is the Pioneers marketing site only) stands.
- The Connect X1 website carries its own product pages, packages and pricing (D-027/D-028), the no-registration explore journey with Carminta answering feature questions (D-024), and checkout.
- Open (to confirm with Shaheen): the domain name and its purchase (needs explicit approval); whether Connect X1 is a separate legal entity or a Pioneers product brand (D-028 says Pioneers invoices as an Egyptian company); whether its modules and add-ons still appear on the Pioneers Add-on Store (D-022) or only on the Connect X1 site; trademark clearance for "Connect X1"; brand identity (logo, colours) separate from Pioneers; email domain for support and customer service.

## D-030 — Connect X1 brand details, domain and tenant addresses (2026-10-02, approved by Shaheen; completes D-029)
These answer `projects/connect-x1/open-questions.md` Q50–Q56.
- **Domain:** `connectx1.com`, **registered by Shaheen at Hostinger** on 2026-10-02 (expires 2027-10-02; transfer lock on). Email is on Hostinger: MX, SPF, DKIM (selector `hostingermail-a`, RSA key; `-b` and `-c` are rotation placeholders) and DMARC (`p=none`, monitoring only) are published. Move DMARC to `quarantine` once mail flows cleanly. Checked in the registry and public DNS on 2026-10-02.
- **Legal status:** Connect X1 is a **product of Pioneers**, not a separate company. Pioneers (an Egyptian company) invoices, as in D-028.
- **Store listing:**
  - Connect X1 features and add-ons are sold in an Add-on Store on the Connect X1 website.
  - Separable modules (for example the Financial system, and HR per D-026) are also listed on pioneers.services as Pioneers products (D-022).
- **Trademark:** "Connect X1" is registered in each launch country later, after launch. Until then, the name carries an unregistered-trademark risk.
- **Brand identity:** Connect X1 gets its own identity (logo, colours), separate from Pioneers. The design system and prototype get rebranded once it exists.
- **Support email:** `support@connectx1.com`. D-028's seat-change requests go here.
- **Tenant addresses:** every customer gets an address on the shared domain, for example `akahomes.connectx1.com`. As soon as payment is confirmed, the customer's dashboard opens directly for implementation (setup journey, D-024).

## D-031 — Connect X1 Wave 1 timeline: 18 weeks (2026-10-02, approved by Shaheen; replaces the ~10-week plan in D-024/D-026)
| Phase | Weeks | Scope | Done when |
|---|---|---|---|
| 1. Discovery & design | 1–2 | Workshops with both pilots using their real Excel/Word files; architecture map (D-020); Bahrain VAT rules checked against NBR; screen designs; AWS Bahrain foundation after cost approval (D-025) | Map checked and designs approved by Shaheen |
| 2. Foundation | 3–4 | Tenants, Owner role with 2FA, users, roles, permissions, hierarchy, audit log, seat billing and the D-027/D-028 rules | Tenant isolation tested |
| 3. Setup journey & Carminta | 5–6 | Explore without registration on the Connect X1 website (D-029/D-030), payment, country → tax/currency, branding, versioned steps, company.connectx1.com; Carminta as setup guide and document reader, with usage metering | A test company set up end to end by Carminta |
| 4. Sales | 7–8 | Leads, customers, estimates/BOQ, quotations with revisions and approvals, branded PDFs | Lead → client-approved quotation |
| 5. Projects | 9–10 | Stages, drawings register, measurements, snags and handover, deposit gate, dashboard; **basic payment recording and allocation for deposits** (amended 2026-10-02, Q57) | Sales and Projects tested end to end on test data (early pilot access removed by D-032) |
| 6. Purchasing & stock | 11–12 | Suppliers, purchase orders, goods receipt, stock on hand vs promised, supplier bills, cost per project | Committed cost visible per project |
| 7. Finance & VAT | 13–15 | Tax invoices, pro-forma, credit limits, retention, post-dated cheques, full payments (reversals, refunds, ledger posting of payments recorded since week 9), chart of accounts, journals, ledger, P&L, balance sheet, reconciliation, lock dates, NBR VAT return (boxes 1–17), profit per project | Figures reconcile on test data |
| 8. Hardening | 16–17 | Bahrain accountant review; security review; restore drill; speed tests from Bahrain; Arabic checks; bug fixing | Accountant signs off; restore tested |
| 9. Go-live | 18 | Studio opening balances, training, parallel run, go-live; AKA follows | Studio runs a real month on Connect X1 |
- Later waves (indicative): Wave 2 ≈ months 5–8 (production pipeline & cutlists, site management, variations, Carminta daily watching, client portal, WhatsApp); Wave 3 ≈ months 9–12 (HR & payroll with Bahrain rules, budgeting, warranty, more country tax packs, other add-ons).
- **Amendment (2026-10-02, approved by Shaheen; Q57 option b):** the deposit gate needs payment records, so basic payment recording and allocation for deposits move into phase 5 (weeks 9–10). Their rules (cleared vs received, allocation, idempotency) are written and reviewed before week 9. Phase 7 completes reversals, refunds and ledger posting.
- Unchanged rules: if a phase slips, accounting reports slip before tax-invoice correctness; nothing goes live without the accountant's sign-off and a tested restore.

## D-032 — Connect X1 launch and subscription rules; DNS plan approved (2026-10-02, approved by Shaheen)
- **No customer uses Connect X1 until it's finished and ready.** This removes D-031's week-10 early pilot access. The first real use is go-live (phase 9, week 18), after the accountant's sign-off and a tested restore. The basic deposit payments in weeks 9–10 (D-031 amendment) stay in place, so the deposit gate is complete and tested before go-live.
- **Connect X1 subscriptions can't be cancelled or refunded.** A subscription runs its full term. D-028's account-closure settlement still applies to a customer who stops paying. Each launch country's consumer-protection rules get checked in the legal review (Q30). This doesn't affect refunds that tenants give their own customers inside the product.
- **Checkout data handling approved:** a requested address is held for 30 minutes during checkout, and unpaid checkout records are deleted after 30 days, pending the legal review. A tenant only becomes active after the payer verifies their email and sets up two-factor login (team review S04).
- **The DNS plan for connectx1.com is approved** (`architecture-map.html`, PR #2): DNS stays at Hostinger, and the live email records stay unchanged. Each new record is added only when its service is deployed, and confirmed with Shaheen at that time.

## D-033 — Connect X1 brand identity: "Studio" (2026-10-02, approved by Shaheen; completes D-030 brand identity)
- Shaheen chose brand direction **C, Studio**, from seven options (A–G): a "connected rooms" mark (2×2 rooms, two outlined and two filled, arranged diagonally so they read as an "x"), with a lowercase wordmark "connect x1" where "x1" is set in coral.
- Palette: Forest #173B36 (primary), Coral #E58C6A (accent), Stone #E9E5DD, Sage #7FA89E, Ink #14211F. Text-safe shades: Coral text #C65023, Sage text #557E74. White never sits on Coral (2.53:1); main buttons are Forest with white text (12.24:1). Pioneers navy and gold are not used.
- Typeface: Readex Pro (Arabic and English, SIL OFL). Wordmarks are outlined paths, so they don't depend on an installed font.
- Kit: `~/Pioneers/brand/connect-x1-studio-v1/` (logos, app icon, favicon, PNGs, `tokens.css`/`tokens.json`, README with contrast rules, `build.py`). The Connect X1 design system and prototype replace their "Pioneers ERP" placeholders with this kit.
- Open: a pre-launch trademark search is recommended; an Arabic wordmark lockup is optional.

## D-034 — Every tenant customises its own brand guideline (2026-10-02, approved by Shaheen; extends D-024 branding step)
- Each customer sets up its **own brand guideline** inside Connect X1: logo (light/dark/mono), colour palette, typography choice, and document styling. It applies to everything the customer's clients and staff see from that company: quotations, invoices, pro-forma invoices, purchase orders, delivery notes, handover certificates, emails, the client portal, and the app theme for its own staff.
- The brand guideline is set during setup (step 4, D-024), where Carminta proposes it from uploaded logo/brand files. The owner approves it, and it can be edited and versioned later; the version in force is kept with each issued document.
- Guard rails (fixed core): contrast is checked automatically, and colour pairs that fail WCAG AA for text are blocked, with Carminta suggesting the nearest passing shade; document layouts keep the legally required tax-invoice fields (A1/NBR) whatever the styling; fonts come from a supported Arabic and English list (licensing).
- Connect X1's own brand (D-033) stays on the platform shell: sign-in, billing and the Connect X1 website.
- Open: how far white-labelling goes (whether a "Powered by Connect X1" mark appears on client-facing documents and the portal, and whether it can be removed for a fee); whether customers can upload their own font files (licensing and Arabic coverage).

## D-035 — Connect X1 discovery without pilot files; accountant audits at the end; AWS foundation approved (2026-10-02, approved by Shaheen)
- **No pilot files.** Discovery uses Pioneers' own knowledge of the interiors workflow and synthetic sample data, not the pilots' real Excel or Word files. The phase 1 exit gate (D-031) becomes Shaheen's approval of the map and screen designs. Anything a pilot's real data would have confirmed stays marked as an unknown in `open-questions.md`, following D-020.
- **The Bahrain accountant audits after the product is finished** (phase 8, weeks 16–17), not during specification. The financial rules (payments, deposits, VAT, posting) are written from NBR sources (`projects/connect-x1/phase-1/nbr-vat-findings.md`) and audited then. Risk accepted: corrections found in the audit may cause rework late in the plan. Tax-invoice correctness still can't slip, and nothing goes live without the accountant's sign-off (D-031).
- **The AWS foundation in Bahrain (`me-south-1`) is approved** at about $2.40/month: network, container registry, encryption key, container cluster, logs and an activity trail (D-025). Development environments are approved separately when the build starts.

## D-036 — Connect X1 colours: "Graphite and teal" (2026-10-02, approved by Shaheen; replaces the D-033 palette)
- Shaheen found the Studio colours (Forest, Coral, Stone) not professional enough for an ERP and chose **option C, Graphite and teal**, from three options (A slate and cobalt, B light and azure, C graphite and teal).
- **Palette:**
  - frame: Graphite #1F2328 (sidebar and text) on cool greys (#F7F7F8 page, #FFFFFF panels, #E4E4E7 lines);
  - action: Teal 700 #0F766E with white text (5.47:1), Teal 500 #14B8A6 for marks and indicators only;
  - Carminta X1 only: Honey #F59E0B with Graphite text (never white);
  - status colours: green success, orange warning, red danger, blue info.
  Dark mode mirrors this, using graphite surfaces and lighter teal. Every text pair passes WCAG AA, checked by script.
- **Kept from D-033:** the Readex Pro typeface, the "connected rooms" mark and wordmark (now Graphite with a teal "x1"), and the bee mascot (now honey and graphite). Pioneers navy and gold still aren't used.
- **Applied to:**
  - the Connect X1 design system (version 8);
  - the prototype (`tokens.css`, icons, logo, bee).
  The brand kit `~/Pioneers/brand/connect-x1-studio-v1/` still has the D-033 colours and needs regenerating by its owner.

## D-037 — Connect X1 hosting region moves to AWS Mumbai, backups in Frankfurt (2026-10-02, approved by Shaheen; replaces D-025's regions)
- **Why:**
  - **Bahrain (`me-south-1`)** is unavailable. AWS's public status page says the region was damaged in the Middle East conflict. Its 15 September 2026 update says AWS can't restore resources or data held only in that region.
  - **UAE (`me-central-1`)** is damaged too. AWS recommends moving workloads out of it.
  - D-025 had been decided without the hosting test, so this wasn't caught until the first deployment attempt. That attempt timed out at sign-in, and nothing was created.
- **New regions:**
  - home: **Mumbai `ap-south-1`** (application, database, files, logs);
  - backups: **Frankfurt `eu-central-1`**, on a separate continent.
  The stack is unchanged: ECS Fargate (ARM), RDS PostgreSQL, Vercel for screens.
- **Measured:** connection time from Shaheen's Mac in Bahrain on 2026-10-02 (TCP connect, three tries each, first try discarded):
  - Mumbai about 61–66 ms;
  - Frankfurt about 124–213 ms;
  - Tel Aviv about 196–252 ms.

  The earlier estimate for Mumbai was 30–50 ms. Screen design should keep the calls a page makes one after another to a minimum.
- **Cost:** the foundation approved in D-035 stays at about $2.40/month in Mumbai. Later costs come from the Mumbai price list and are approved when they're added.
- **Data location changes:** tenant data is stored in India, with backups in the EU, not in the Gulf. This replaces the data-location note added to D-025 for review point R22. The per-country legal review (Q30) must confirm cross-border transfer for every launch country before go-live: Bahrain, KSA, UAE, Oman, Kuwait and Egypt.
- **Lesson:** check the provider's status and region health before deciding on hosting or deploying anything.

## D-038 — Connect X1 phase 1 approved: map and screen designs (2026-10-02, approved by Shaheen; closes the D-031 phase 1 gate as set by D-035)
- **Approved screen designs** (in the `prototype/` folder of the connectx1 repo, Graphite and teal palette D-036, synthetic data):
  - company setup (nine steps, contrast-checked brand guideline);
  - project workspace (nine stages, drawings register, measurements, budget vs committed vs actual);
  - purchasing (orders per project, goods receipt, three-way match);
  - quotation with revisions and the advance tax invoice with the NBR Article 52(A) field check;
  - the earlier CRM screens: leads, quotations, job and deposit gate, production, settings, audit and Carminta.
- **Approved map:** `architecture-map.html` is updated to match. A new §8 ties each screen to its modules and flows, and the status is now "phase 1 approved". Unknowns are unchanged: 23 open, Q1–Q59.
- **Correction:** the NBR VAT return has **18 boxes** in the January 2022 filing manual, not "boxes 1–17" as D-021 and D-031 say. Project docs now say 18; the accountant confirms against the live portal (D-035).
- **Next:** phase 2 (weeks 3–4), the foundation build:
  - tenants, the Owner role with two-factor login, users, roles and permissions, hierarchy and the audit log;
  - seat billing (D-027, D-028);
  - tenant isolation tested.

  It is built on the Mumbai foundation (D-037). Each new AWS resource still needs an itemised cost approval.

## D-039 — Connect X1 sign-in is built by Pioneers (2026-10-02, approved by Shaheen; resolves Q11)
- **Sign-in and two-factor login are Pioneers' own code on the Connect X1 database.** There is no outside identity product such as Cognito. This follows Shaheen's rule that everything is built by Pioneers.
- **Fixed core** (no tenant can turn these off):
  - passwords hashed with Argon2id;
  - two-factor login with an authenticator app (TOTP), required for every Owner (D-024);
  - session tokens stored only as hashes, revocable, with idle and absolute expiry;
  - account lockout after repeated failures;
  - every sign-in event in the audit log;
  - Pioneers support never holds an Owner membership.
- **Cost:** none.
- **Accepted trade-off:** Pioneers owns the security of this code. It gets negative tests in phase 2 and an independent security review in phase 8 (D-031).
- **Email for invitations and password resets (Q12)** stays open. Phase 2 uses a development outbox that sends nothing; the provider is chosen before phase 3.

## D-040 — Connect X1 development environment on AWS (lean); system email through Hostinger (2026-10-03, approved by Shaheen; resolves Q12)
- **Development environment in Mumbai, lean option:** about $19–25 per month, on top of the $2.40 foundation (D-035, D-037).
  - **Database:** RDS PostgreSQL 17, db.t4g.micro, single zone, 20 GB gp3, encrypted with the Connect X1 key, private subnets only, 7-day backups. About $18.35 per month including the managed admin secret.
  - **API container:** ECS Fargate ARM, 0.25 vCPU and 0.5 GB. It runs only for jobs such as migrations and the test suite, so it costs cents per run. It accepts no incoming connections. While a job runs it gets a temporary public IP for outbound access to the image registry (no NAT gateway or paid endpoints), costing cents per run.
  - **Secrets:** SSM Parameter Store SecureStrings (free), encrypted with the Connect X1 key.
  - Prices come from the AWS Price List API, Mumbai, 2026-10-03.
- **Not yet created:** the load balancer, HTTPS and `api.connectx1.com` (about $35 per month more). They get their own approval when the sign-in screens are ready. The two DNS records they need at Hostinger are confirmed with Shaheen at that time (D-032).
- **System email (Q12):** sent by SMTP through the Hostinger mailbox `support@connectx1.com`. Shaheen confirmed it works on 2026-10-03.
  - The Business Starter plan allows 1,000 messages a day, enough for invitations and password resets in the pilot.
  - Replies arrive in the support inbox.
  - SPF and DKIM are already set for Hostinger (D-030).
  - The mailbox password is stored by Shaheen in Parameter Store and never passes through chat or Git.
  - Revisit if volume grows, or if system mail should move to the `mail.` subdomain set out in the DNS plan.

## D-041 — Connect X1 phase 2 (foundation) complete; merged to main (2026-10-03, approved by Shaheen: "if 100% done merge to main")
- **Audit:** `phase-2/audit.md` in the connectx1 repo. Every scope item in D-031 phase 2 has database rules, an API, a screen and tests:
  - tenants;
  - Owner with 2FA;
  - users;
  - roles and permissions;
  - hierarchy;
  - audit log;
  - seat billing with the D-027/D-028 rules.
- **Gaps closed during the audit:** hierarchy and audit screens; the D-027/D-028 pricing engine and seat-change rules; a billing date shifted by a day in UTC+3.
- **Exit gate met:** company isolation tested.
  - 38 of 38 tests pass locally, three runs in a row.
  - The isolation suite passed 24/24 on AWS RDS in Mumbai.
  - The independent security review is fixed: 3 high, 3 medium, 3 low (`phase-2/security-review.md`).
- **Seat billing calculates and enforces the rules, but no payments are taken yet** (Q31). Prices are in BHD only until Q48 is answered.
- **Next:** phase 3 (weeks 5–6) — setup journey, payment, and Carminta as setup guide. The load balancer, `api.connectx1.com` and Vercel get their own cost approval when needed.

## D-042 — Connect X1 branding rules for tenants; legal review done (2026-10-03, approved by Shaheen; resolves Q58, Q59, Q30)
- **Q58 White-labelling: yes.** Tenants apply their own logo, colours and documents (D-034).
  - **Shared hosting:** a small "Powered by Connect X1" mark always stays on client-facing documents and the client portal. It can't be removed.
  - **Dedicated hosting** (the +75 / +120 BHD option, D-027): full white-label, and the mark can be removed. No separate fee.
- **Q59 Customer fonts: no uploads.** Tenants choose only from the Connect X1 supported font list. This avoids font-licence risk and keeps Arabic coverage checked.
- **Q30 Data protection:** Shaheen confirmed on 2026-10-03 that the legal review is done for the current hosting (data in Mumbai, backups in Frankfurt; D-037). File the written outcome in the connectx1 repo next to `open-questions.md`.

## D-043 — Connect X1 launch countries: all open at checkout, Libya added (2026-10-04, approved by Shaheen)
- **Launch countries are now seven:** Bahrain, Saudi Arabia, UAE, Oman, Kuwait, Egypt and **Libya** (new).
- **Every launch country can check out now.** The company works in its own currency (BHD, SAR, AED, OMR, KWD, EGP, LYD). Its subscription is billed in BHD until local prices are set (Q48).
- **A company goes live only when its country's tax pack is ready.** The pack must be checked against that tax authority's sources, so the company never issues tax invoices its government rejects. Setup can be finished before that.
- **Today only Bahrain's pack is ready.** What each of the others needs (sources checked 2026-10-04):

| Country | Currency | VAT | E-invoicing the tax pack must connect to |
|---|---|---|---|
| Saudi Arabia | SAR | 15% | ZATCA Fatoora integration phase; the next wave must integrate by 1 February 2027 |
| Egypt | EGP | 14% | ETA e-invoice and e-receipt clearance (mandatory for B2B since 2023) |
| Oman | OMR | 5% | Mandatory e-invoicing from April 2027 (OTA Decision 189/2026) |
| UAE | AED | 5% | None in this pack yet |
| Kuwait | KWD | none | None |
| Libya | LYD | none | None |

- **Consequence for the plan:** the Saudi and Egyptian packs are integration projects. They aren't a settings change, and they need their own scope and schedule before those customers can go live (the D-031 plan has other countries' tax packs in Wave 3).
- **VAT numbers:** Bahrain's format (15 digits) is enforced. The other countries' formats are verified when their packs are built. No VAT number is accepted in Kuwait or Libya.

## D-044 — Connect X1 integrations: one connection layer, four priority integrations (2026-10-04, approved by Shaheen)
- **One connection layer, built by Pioneers**, so every integration has the same safeguards:
  - each company's credentials encrypted;
  - an outbox with safe retries;
  - a sync log in the audit trail;
  - the same permission checks as the screens (Carminta can't use a connection to get around them);
  - the core keeps working when an outside service is down.
- **Priority integrations, all four chosen by Shaheen, in this order:**
  1. **Government e-invoicing.** ZATCA (Saudi Arabia) and ETA (Egypt), then Oman from April 2027. Each completes that country's tax pack (D-043) and must be live before that country's first customer goes live.
  2. **Bank statements.** Import from Bahrain banks in phase 5; payment matching and reconciliation in phase 7.
  3. **WhatsApp Business.** Quotations, invoices, reminders and approval links, in phases 5–6. This moves A4 earlier than Wave 2.
  4. **Open API and webhooks.** Per-company scoped keys and event webhooks, in phase 6.
- **The connection layer itself comes first, in phase 4.**
- **Outside steps needed from Pioneers or the pilots:**
  - a WhatsApp Business account with Meta verification;
  - sample statement formats from the pilots' banks;
  - ZATCA and ETA onboarding for each company in those countries.
- **Schedule:** the 18-week plan (D-031) stays. If a phase slips, the accounting reports slip first, and tax-invoice correctness never slips.

## D-045 — Connect X1 app and social integrations, extending D-044 (2026-10-04, approved by Shaheen)
All of these run on the D-044 connection layer and are offered through the Add-on Store (D-022). Each company signs in to each app itself and can revoke access at any time.

| Integration | What it does | When |
|---|---|---|
| Instagram and Facebook leads | Messages, comments and lead forms become leads in Sales, with the source recorded. Uses the same Meta Business account as WhatsApp; needs Meta app review | Phase 4 (Sales) |
| Google and Microsoft calendar and email | Site visits, measurements and handovers in staff calendars; quotation emails logged on the customer | Phase 5 |
| Cloud storage (Google Drive, OneDrive, Dropbox) | Link or import drawings and photos to a project | Phase 5 |
| Design files: SketchUp, AutoCAD, 3ds Max | Stored and versioned in the drawings register, with previews from their exports (PDF, PNG, glTF) | Phase 5 |
| Design files: DXF | Read for cutlists and quantities (A9) | Wave 2 |
| Design files: DWG and SketchUp contents | Read the files directly. **Needs a licensed reading library or SketchUp's developer kit, which Shaheen approves before use** (the first outside component under the "built by Pioneers" rule) | Wave 3 |
| Slack | Project, approval and finding notifications to the company's own channels | Wave 2 |
| Notion | Project summaries and tasks synced to the company's workspace | Wave 2 |
| Google Business Profile | Reviews and enquiries; Carminta suggests a review request after handover | Wave 2 |

- **"And more":** further apps connect through the open API and webhooks (D-044). Customers can link other tools themselves, and Pioneers adds native connectors when several customers ask for the same app.
- **Not planned:** posting to social media from Connect X1. An ERP isn't a posting tool.

## D-046 — Connect X1 subscription payment methods: cards plus each country's local methods (2026-10-04, approved by Shaheen; shapes Q31)
- **Methods offered:** Visa and Mastercard in every country, plus each country's local methods, plus bank transfer everywhere.

| Country | Local methods |
|---|---|
| Bahrain | BenefitPay, Apple Pay |
| Saudi Arabia | mada, Apple Pay, STC Pay |
| UAE | Apple Pay |
| Oman | OmanNet |
| Kuwait | KNET, Apple Pay |
| Egypt | Meeza, mobile wallets, InstaPay (launching on Paymob) |
| Libya | Moamalat Libyan cards |

- **One payment adapter routes each method to a provider.** Candidates per method are listed in `api/src/payment-methods.ts`: Tap (BenefitPay and the GCC), Paymob (Egypt), MyFatoorah (KNET, OmanNet), Moamalat (Libya). The providers themselves are still to be chosen and contracted (Q31 stays open for that).
- **Local methods charge only in local currency.** Subscriptions are billed in BHD until local prices exist (Q48), so:
  - in Bahrain, all methods work;
  - elsewhere, only cards and bank transfer work for now;
  - mada, KNET, OmanNet, Meeza, wallets, InstaPay and Moamalat open when local prices are set.

  **Q48 now blocks local methods outside Bahrain.**
- **Bank transfer:**
  - The payer quotes a short reference (CX-XXXXXXXX).
  - Pioneers billing confirms the transfer, and the company is then set up through the same safeguards as card payments: amount and currency checked, address checked, once only.
  - Pioneers' receiving bank details are set per environment (`CX_BANK_DETAILS`).
- **Open for Shaheen:**
  - **Merchant entity:** Pioneers invoices as an Egyptian company (D-028), and most GCC local methods need a local merchant account. Which entity holds each country's merchant account?
  - **Bank-transfer address hold:** the address hold is 30 minutes (D-032), and a transfer can take days. Should a bank-transfer checkout hold the address longer?

## D-047 — Connect X1 local prices, receiving accounts and bank-transfer timeline (2026-10-04, approved by Shaheen; amends D-032; resolves the approach for Q48)
- **Local prices (Q48 approach):**
  - Each launch currency gets a fixed price list: the BHD list (D-027) converted at a reference rate and rounded to clean amounts.
  - The BHD 8 per-seat floor (D-028) is converted the same way and rounded up.
  - Lists are reviewed every quarter.
  - **A list is used only after Shaheen approves its numbers.** The proposal is `phase-3/local-prices-proposal.md` in the connectx1 repo.
  - Until a list is approved, that country is charged in BHD.
  - Once approved, the country's local payment methods open (D-046).
- **Receiving accounts, for now:**
  - Shaheen's personal bank account in Bahrain (for BHD) and his personal account in Egypt (for EGP) receive bank transfers.
  - A Pioneers branch in Bahrain may follow and would take over.
  - The account details are stored as environment secrets (`CX_BANK_DETAILS_BHD`, `CX_BANK_DETAILS_EGP`), never in Git or chat.
  - **Risks noted:**
    - Card and local-method gateways generally require a registered business, so online methods wait for a business entity.
    - Company income received into personal accounts has tax and record-keeping consequences in Bahrain and Egypt, which the accountant should review.
- **Bank-transfer timeline** (amends D-032's 30-minute hold for bank transfers only):
  - The address is held for 7 days.
  - If no transfer is confirmed after 7 days, management is warned by email. That's one warning, sent to `CX_MANAGEMENT_EMAIL`, by default `support@connectx1.com`.
  - After 14 days the checkout is frozen and the address released. A transfer that arrives later is handled by management (refund, or a new checkout).
  - The daily job is `follow-up-transfers`.

## D-048 — Connect X1 prices in USD terms and a pricing dashboard for management (2026-10-04, requested by Shaheen; amends D-047)
- **USD is the base for every rate:**
  - The BHD list (D-027) stays the master. It is converted to USD at the 0.376 peg, then to each billing currency, and rounded to a clean step.
  - Billing currencies:
    - Bahrain: BHD
    - Saudi Arabia: SAR
    - UAE: AED
    - Oman: OMR
    - Kuwait: KWD
    - **Egypt and Libya: USD.** There are no EGP or LYD price lists, and transfers from those countries are made in USD.
  - Local methods that charge only in EGP or LYD (Meeza, Egyptian wallets, InstaPay, Moamalat) stay unavailable until a provider can charge them in USD.
- **Pricing dashboard** (`/admin/pricing`, for Pioneers staff only):
  - Staff draft price lists per currency, from a USD rate or edited by hand.
  - Staff draft offers per country: a first-year discount of 0–60%, 0–3 free months on yearly payment, a label and an optional end date.
  - **A Pioneers manager approves.** Drafts are never used, and approved versions can't be edited; a change is a new version.
  - Until a currency has an approved list, its countries are billed in BHD.
  - Without an offer, there is no discount and yearly payment gets 2 free months.
- **Existing customers keep their prices:** each subscription records the list and offer it was sold on.
- **Who has access:**
  - Pioneers staff use two-factor login.
  - Staff roles are set only by the `platform-role` job, never through the app.
  - A company owner can't be Pioneers staff (D-024), so Shaheen needs a separate staff account.
  - Every draft, edit and approval is audited.
- **Receiving accounts (D-047):** the USD account details go in `CX_BANK_DETAILS_USD`, an environment secret set by Shaheen.
- **Starting drafts:** `phase-3/local-prices-proposal.md` in the connectx1 repo.
- **Amended 2026-10-04 (Shaheen):**
  - Prices are set per country, not per currency.
  - One **USD main list** is edited directly.
  - Each country's list is worked out from the main list at its rate and can then be edited. Egypt and Libya each have their own USD list.
  - Drafts can be edited, recalculated or deleted. Editing an approved version starts a new draft.
  - A manager can end an approved offer early. Customers who already have it keep it.

## D-049 — Connect X1 phase 3 (setup journey and Carminta) complete; merged to main (2026-10-04, approved by Shaheen: "Merge")
- **Merged:** PR Pioneers-services/connectx1#6. Audit in `phase-3/audit.md`.
- **Exit gate met:** a test company is set up end to end with Carminta's guidance: checkout → payment → owner invitation → two-factor login → setup steps → live.
- **In scope and done:**
  - the public plans page and checkout (D-029, D-030, D-032);
  - payment methods per country (D-046);
  - bank transfer with its 7- and 14-day timeline (D-047);
  - 7 launch countries with tax packs (D-043);
  - versioned setup steps with owner approval;
  - branding (D-034, D-042);
  - Carminta as setup guide and document reader, with metering;
  - the pricing dashboard (D-048).
- **Verification:**
  - 76/76 tests locally and on AWS RDS in Mumbai (image e335c8724141, migrations 003–012);
  - the independent security review is fixed (`phase-3/security-review.md`).
- **Still waiting on providers:**
  - the payment provider (Q31): checkout uses a test provider and bank transfer;
  - the AI model (Q13: Bedrock in Mumbai, waiting on AWS).
- **Deferred:**
  - the `cx_migrator` role (phase 8);
  - putting the app online on AWS (load balancer, `api.connectx1.com`, web hosting), which gets its own cost approval.
- **Next:** phase 4 (weeks 7–8), Sales: leads, customers, estimates/BOQ, quotations with revisions and approvals, branded PDFs.

## D-050 — Connect X1 Sales design, hosting timing and Carminta's models (2026-10-04, decided by Shaheen)
- **Lead and enquiry are different records:**
  - A **lead** is blind: there has been no meeting yet and there are no specific items. Typical sources are a phone call, WhatsApp, a walk-in, social media or the website.
  - An **enquiry** comes after the sales team has met the customer. They have the customer's details and know the project: the site, the items and the materials.
  - A lead converts into an enquiry.
  - This changes the single "Leads and customers" screen in the approved prototype (D-038).
- **Estimates are priced from measurements and dimensions**, using the AKA v5.3 estimator as the reference:
  - each company has its own versioned rate card, approved by the owner;
  - each product type has a measurement rule: running metre, wall area for straight, L and U shapes, floor area, per unit or per set;
  - option axes (such as collection, door style and height band) select the rate;
  - add-ons are priced per unit.
  - BOQ lines stay available for fit-out contractors.
  - AKA's v5.3 prices become AKA's data, not code (D-014).
  - Leads can get a quick ballpark range.
- **Putting the app online on AWS** (load balancer, `api.connectx1.com`, web hosting) waits until the first release is built. It happens at the start of phase 8 (hardening), after an itemised cost approval. Until then, testing is local and through AWS jobs.
- **Carminta's models (shapes Q13; amends the plan of Claude Haiku and Sonnet):**
  - **Included in every subscription (D-023):** Amazon's own low-cost models on Bedrock run Carminta and all internal tasks.
  - **Premium models are paid add-ons in the Store, under "Carminta models":** Claude and GPT, at an additional fee, metered per company.
  - **To check before building:**
    - whether these models are available to us in Mumbai, and whether requests may be processed in other regions;
    - quality on the Carminta benchmark, including Arabic documents;
    - for GPT, a provider that doesn't train on or keep customer data (D-024).

## D-051 — Carminta's model choice: Asia-Pacific routing, cheapest capable model per tier (2026-10-04, decided by Shaheen; amends D-050, shapes Q13)
- **Routing:** Asia-Pacific cross-region processing on Bedrock is approved. Requests start in Mumbai and may run in other AWS Asia-Pacific regions. This is needed because Amazon Nova is only available in Mumbai through that route.
- **What every tier must handle:** Arabic and English; documents (PDF) and photos; calculations; arranging tasks; building tables; carrying out actions; and knowing Connect X1 and the customer's business.
  - **Calculations** (totals, VAT, measurements, prices) are done by Connect X1 code that Carminta calls, never by the model's own arithmetic.
  - **Actions** go through Carminta's tools, using the user's own permissions and the approve-then-confirm step.
  - **Knowledge** of Connect X1 and the customer comes from the product knowledge base and the tenant's own data, through tools. Nothing is trained into the model.
- **Rule: use the cheapest model in each tier that passes the Carminta benchmark.**
  - **Included tier:** Amazon **Nova Lite**, which reads images and PDFs and calls tools. **Nova Micro** (text only) handles short routing and classification jobs. **Nova Pro** is the fallback if Nova Lite fails the Arabic document tests.
  - **Claude add-on:** **Claude Haiku 4.5**, the cheapest current Claude. It runs on the India-only route, which is stricter than Asia-Pacific.
  - **GPT add-on:** the cheapest current GPT on Bedrock that reads images and documents. It's chosen after a price and feature check. On Bedrock these models run only on the **Global** route, so the add-on's terms must tell the customer their requests may be processed outside Asia-Pacific. No direct OpenAI or Azure contract is needed (D-024).
- **Gate:** none of this is final until the benchmark runs. That waits on AWS raising the account's daily token quota (support case opened 2026-10-03).

## D-052 — Carminta usage allowances and Claude add-on (2026-10-04, decided by Shaheen, relayed by the business-transformation session; amends D-027's 300-request placeholder; metering per D-028)
- **Included tier (Nova Lite, D-051):**
  - **1,000 Carminta requests per user per month**, free in every subscription and pooled per company (Shaheen: "1000 is fair").
  - Paid extra packs are only for heavier use.
  - Estimated cost is about $0.0007 per request, so about $0.70 per user per month.
  - Unchanged: D-028's uncounted first days, the warning at 80%, and Carminta never stops without warning.
- **Claude add-on (Haiku 4.5), confirmed by Shaheen:**
  - **BHD 5 per month for every 5 users, including 900 premium requests per 5 users per month.** That's about 8 per user per working day.
  - Heavier use buys paid packs (D-028).
  - At about $0.01 per request, that's about $9 of cost against $13.26 of revenue: about 32% margin, breaking even near 1,300 requests.
- **GPT add-on:** its price waits for the GPT price on Bedrock.
- **All costs are estimates** until the Carminta bench measures real tokens per request. Revisit them after it runs.

## D-053 — Connect X1 Sales rules: units, ballpark range and quotation approvers (2026-10-04, decided by Shaheen; completes the D-050 Sales design; resolves Q2 for quotations)
- **Units:**
  - All dimensions are entered and stored **in millimetres**.
  - Areas and running metres are worked out from them: m² = mm × mm ÷ 1,000,000, and RM = mm ÷ 1,000.
- **Ballpark range for leads:** set **per company** as a company setting. The default is −15% / +25%, as in AKA v5.3.
- **Who approves a quotation:**
  - **The owner marks it** in the company's rules: which roles may approve quotations, each with an optional amount limit. For example, manager up to BHD 5,000 and owner with no limit.
  - A quotation over a person's limit goes to someone whose limit covers it.
  - Every approval is recorded with who approved, when, and the amount.

## D-054 — Connect X1 screens: one step per page, leads named after the person, project handover, letterheads, a dashboard for each user (2026-10-05, decided by Shaheen; replaces the one-page job layout in D-038)
- **Rejected:**
  - the one-page sales workflow, which was crowded, badly arranged, and had no edit, back or delete;
  - naming a lead after what the customer wants.
- **Every step gets its own page**, with the same page frame:
  - **Back**, **Edit**, **Step back** and **Delete** on every page.
  - Delete is only for records nothing depends on yet. Anything else is cancelled or marked lost with a reason, and stays in history.
- **A lead is named after the contact person.** "Interested in" is a list of any number of items.
- **Handover:**
  - When the invoice (the advance invoice) is created, Connect X1 creates the **project** with a full handover pack.
  - The project page tracks everything about the job, with a tab for each department.
  - The deposit gate still controls production (D-031).
- **Letterheads:**
  - 5 letterhead styles for every generated PDF.
  - Each uses the company's own logo and branding, and can be adjusted.
  - Tax invoices always keep the fields the tax authority requires.
- **Home is a dashboard for each user**, by role.
- **Design:** `phase-4/screens.md` in the connectx1 repo, waiting for Shaheen's approval. Clickable prototypes come before the real screens.

## D-055 — Connect X1 phase 4 screen design approved; numbering settings and a unified job number (2026-10-05, approved by Shaheen; completes D-054)
- **Approved:** the screen design in `phase-4/screens.md` in the connectx1 repo:
  - the numbered workflow steps 1–9;
  - who can edit or delete after each step:
    - **editing:** anyone whose role has Sales access can edit any record they can see. View-only roles can't edit, and every change records who made it. Shaheen decided this on 2026-10-05, replacing AKA v5.3's rule that only the record's owner edits it;
    - **deleting** follows AKA v5.3: a request with a reason plus a second person's approval. It's made stricter in three ways:
    - nothing is erased: deleted records go to a Bin the Owner can restore from;
    - tax documents are never edited or deleted;
    - approval locks a record.
  - the page frame, the home dashboard for each user, the handover, and the letterheads (D-054).
- **Numbering is editable for each company** by the Owner or Admin, for every document type:
  - prefix, year part, digits, separator, restart, next number and an optional branch code;
  - a change applies to the next number only, needs the owner's approval, and is audited;
  - tax series (SI, CN, RV) change only before their first document or from 1 January.
- **Default format:** `PREFIX-YY-NNNN`, made on the server.
  - Tax documents get their number only when issued, with no gaps.
  - Quotations keep one number with revisions R1, R2….
  - AKA's existing numbers are imported unchanged and continue from the highest.
- **Everything stays editable (Shaheen, 2026-10-06):** anyone with Sales access can correct any sales record at any stage.
  - Editing a sent or accepted quotation automatically makes the next revision, and the old one stays readable.
  - A completed site visit can be corrected, with a reason.
  - The only hard lock is an issued tax invoice or credit note, which is corrected with a credit note.
  - This replaces "approval locks a record".
- **Unified job number: on by default, and a company setting.**
  - One job number from the enquiry onwards is shared by the enquiry, site visits, estimates, quotation, order and project (SE, MS, ES, QT, SO, PJ).
  - Leads, tax invoices, receipts, credit notes and purchasing documents keep their own series, and show the job number.
- **Branches, decided by Shaheen on 2026-10-05:**
  - **Numbering:** one series for the whole company, with the branch code in the number (`SE-MNM-26-0042`).
  - **Visibility:** staff see only their own branch by default; managers and the owner see all branches.
  - **Tax invoices:** the series follows the legal entity unless the accountant confirms otherwise (Q14).

## D-056 — Connect X1 menus by role, private costs, invoices in Sales, direct quotations, projects by department (2026-10-07, decided by Shaheen after reviewing the prototype; follows AKA v5.3)
- **Menus by role:** each role sees its own menu: sales, sales manager, accountant, project and production manager, view only, and owner. This follows AKA v5.3's per-role menus.
- **Leads and customers are separate.** Enquiries and quotations can start **without a lead**, as in AKA v5.3, where a quotation links to an enquiry only if one exists. A direct quotation creates its enquiry and job number automatically.
- **Invoices are in Sales.** The accountant has full access to quotations, invoices and payments. Issued tax invoices are corrected only with credit notes.
- **Costs and margins are private to the Owner and the accountant.** Staff see selling prices only. This follows AKA v5.3, where only admin, owner and IT see costs.
- **Projects:**
  - A project opens when the advance invoice is issued.
  - Each department works in its own tab: Sales handover, Design, Production, Purchasing, Finance.
  - Production and purchasing see quantities, never prices or profit.
  - The project manager accepts the handover against a checklist.
- **Every list page starts with a summary of counts and money.**
- **Design:** section 0b of `phase-4/screens.md`. The prototype is `prototype/sales.html`.

## D-057 — Connect X1 full quotation and enquiry pages, site visits in Operations, targets, reports, pricing system, invoice amendment (2026-10-07, decided by Shaheen after reviewing the prototype; follows AKA v5.3)
- **Quotation page:** a full builder like AKA v5.3's quotation builder.
  - Customer and project details, a description, and a validity period.
  - Lines priced from the pricing system or entered by hand.
  - Line and overall discounts, VAT, round-off and a VAT calculator.
  - A payment schedule, notes for the customer and internal notes, terms templates and exclusions.
  - Revisions, history and the PDF preview.
- **New enquiry and new quotation are full pages** with AKA's enquiry fields: customer, project, items with options and mm dimensions, a site-visit request, attachments and notes.
- **Site visits are part of Operations:**
  - Sales request them from the enquiry.
  - The measurement team books and completes them.
  - Each visit produces a measurement sheet PDF.
- **Designers are users** with the Designer role. They're chosen from a list, or entered as an external designer.
- **Every list has search, filters and export.** Reports include a pivot table.
- **Sales targets:** monthly, per salesperson, measured on money received before VAT, as in AKA v5.3.
- **"Pricing system" replaces "rate card":**
  - products, options and prices;
  - add-ons;
  - the quick estimator;
  - discount and approval limits;
  - terms templates;
  - a calculator;
  - the change history.
- **Editing an issued tax invoice:** Connect X1 issues the credit note and the corrected invoice in one step, moving payments across. This keeps it compliant without making the user handle the credit note separately.
- **Design:** section 0c of `phase-4/screens.md`. The prototype is `prototype/sales.html`.

## D-058 — Connect X1: enquiry versus quotation, products dashboard with shapes, customer entered once, measurement timeline, pro-forma and receipts, bilingual letterheads on every document (2026-10-07, decided by Shaheen after reviewing the prototype)
- **The enquiry holds the requirements and has no prices.** It covers rooms, products, types, shapes, materials, specifications, measurements and files. **The quotation prices it.**
  - Both carry the same job number.
  - A quotation made without an enquiry opens a job on the spot and takes that job's number. So do the measurement file, the pro-forma (with a suffix) and the project.
- **Products dashboard** with categories, types, shapes, materials, specifications, descriptions and the room list.
  - Kitchens: straight, L, U, G, parallel or with an island.
  - Wardrobes: straight, L, U or walk-in.
  - Enquiry items are picked from these lists.
- **A customer is entered once and read live everywhere.** Search works as you type and includes open leads.
  - Exception: an issued tax invoice keeps the details it was issued with. Changing them goes through a credit note.
- **Full pages:** new lead, new enquiry, new quotation, and editing requirements. No descriptions under page titles.
- **Leads:**
  - No update for 30 days: the owner is asked for one.
  - 45 days: the lead moves to Pending, an archive kept off the active list.
- **Measurements belong to the measurement department.** Sales only request them; the department arranges the date with the customer.
  - One file per job, as a timeline: initial measurement, then power and plumbing points, then final measurement.
  - Each visit has its own date, person, notes, and photos and PDFs.
- **Invoices:**
  - Pro-forma, tax invoice, credit note and receipt, listed by month.
  - Payment on a pro-forma issues the tax invoice and the receipt together, because VAT is due on receipt.
  - Receipts have their own series.
  - Payments received show the salesperson and branch.
- **Project page:**
  - key figures, and planned and actual dates;
  - team, documents and the readiness checklist.
  The project manager marks each milestone.
- **Targets setup** (owner and sales manager): yearly grid, activity targets, what counts as achieved, and commission tiers.
- **Letterheads apply to every document:** English, Arabic (right to left), or Arabic right and English left on the same page.
  - 6 styles.
  - Company names in both languages, fonts, colours, stamp and signatory.
  - QR code and bank details on tax documents.
- **Design:** section 0d of `phase-4/screens.md`. The prototype is `prototype/sales.html` (commit 45049dc).
- **Follow-up (2026-10-08, Shaheen):**
  - No payment schedule on quotations.
  - "Estimated value" replaces "Ballpark".
  - The project timeline follows AKA v5.3's order, with an owner per step: design drawings, final measurement, design updated, production drawings, customer signature, production, quality check, delivery, installation, handover, snags.
  - "Payments" replaces "Money".
  - Bilingual documents put English on the left and Arabic on the right of every line.
