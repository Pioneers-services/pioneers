# Carminta roles and boundaries
Status: Agreed direction; runtime implementation not started

## Carminta
Pioneers' private engineering/orchestration system and envisioned character. Uses specifications, isolated coding workspaces, approved tools and reviewable releases. Public character presence, if built, is separated from internal systems and customer records.

## Carminta X1
Connect's company implementation and operations assistant. One maintained runtime with company-isolated context; not a model deployment or code fork per customer. Uses existing supported actions to configure branches, workflows, price lists and company information. Model APIs are replaceable; Pioneers owns the product logic and orchestration.

## Runtime cycle
Detect → explain → assign → propose → approve → execute → verify → remember → learn → propose improvements.

Deterministic scanner finds exact integrity issues. AI can explain and suggest uncertain patterns, labeled as suggestions. Tool execution passes through the same secured business services as normal UI actions. Permissions are enforced in code, not merely a prompt. New capabilities return to Pioneers engineering.

## Action Center
Finding identity derives from rule and affected records, not changing text/counts. Include severity, evidence, owner, affected records, recommended actions and rule version. States: open, assigned, action pending, verification pending, resolved; dismissed-with-reason is distinct. Recheck after actions. Sensitive financial operations use correction/reversal where required, not casual deletion.

## Model evaluation
No model is approved as universal winner. Evaluate candidates on identical synthetic/anonymized tasks: Arabic/English, correct tools, incomplete requirements, denied cross-tenant requests, duplicate prevention, partial failures, cost and latency. Model version availability must be verified at selection time. No reliance on unverified provider rankings.
