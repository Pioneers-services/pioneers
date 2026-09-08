# Security and release standards
Status: Proposed implementation standards derived from agreed safety principles

- No secrets, real customer datasets, backup archives or private keys in Git.
- MFA and least privilege for privileged systems; separate environments and integration credentials.
- Dedicated user-management endpoints with explicit allowed fields; never return password hashes.
- Record/action authorization on every API, file and live-update path; test negative access cases.
- Atomic database writes, constraints, transaction-safe numbering and retry idempotency.
- Append-only server-originated audit events; external protection for threat models including privileged compromise.
- Validated output handling, file verification, bounded retries, session revocation and explicit failures.
- No production patching as routine development. Small reviewable branches and migrations with a single owner.
- Feature specification → failing behavioral test → implementation → independent review → integration/browser test → approved release.
- Document commands, actual results and limitations. Syntax checks, line-count changes and AI self-reports alone are not acceptance evidence.
- Isolate coding agents; no default production credentials. Provider diversity can help review but does not replace tests or human domain review.
- Backup database, files and recovery instructions; encrypt independently stored copies; test restoration; monitor failed or stale jobs.
- Purchases and production releases require Shaheen's explicit approval. Branch protection/CI enforcement is not configured merely by writing this policy.
