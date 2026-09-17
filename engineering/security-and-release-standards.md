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

## Model selection for delegated engineering tasks
- Match model capability to task risk and judgment required, not habit or cost-minimization alone.
- Mechanical tasks with one obviously correct answer (git plumbing, a hardcoded-path fix, a repo toggle, a boilerplate CI workflow) go to a fast, cheap model.
- Tasks with real reasoning depth and a security or correctness cost of error (permission logic, auth, data-handling redesigns) go to the most capable model, run at high reasoning effort, given the full task context up front rather than a partial slice.
- Writing and communication tasks (reports, docs, design notes) go to a mid-tier model.
- Every delegated task carries an explicit, falsifiable acceptance test stated before work starts — not "make it work." Same principle as the failing-behavioral-test requirement above, applied to task assignment.
- No agent's self-report is accepted as verification, per the AI-self-reports rule above; this applies regardless of which model produced the work.
- Security- or correctness-sensitive changes get independent re-verification — rerun the test, inspect the actual output file or state directly — before the fix is treated as resolved, regardless of which model produced it.
