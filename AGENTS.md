# Scoped engineering work — arkham

This file governs work in this public repository. Preserve existing documentation and examples; add new revisions deliberately. The engineering package is a proposed implementation design, not application code or proof of a deployed service. Read [the English index](engineering/index.en.md) and existing [public architecture](docs/architecture.en.md) before changing its contracts.

## Responsibilities and evidence

- Use synthetic data exclusively. Do not import private archives, actual case/candidate records, credentials, account identifiers, screenshots or workstation paths.
- Keep English, Brazilian Portuguese and Japanese engineering documents aligned. Non-English documents are explicitly labeled actionable summaries; requirement IDs and normative boundaries must stay consistent.
- Role files in `agents/` specify human or manually assigned work. They do not start agents, schedule jobs, invoke models or authorize integrations. Explicit delegation is required to instantiate work.
- Preserve the separation between proposed behavior, existing public statements and observed results. Record checks as `not_run` until actually executed; schema validation does not prove runtime behavior.
- A changed contract requires an index update, a valid synthetic fixture, a deliberately invalid fixture, documented semantic limits and a validation-case entry. Never weaken a schema merely to make an invalid example pass.
- Stop and report unresolved policy or invariant conflicts. Do not invent operational approvals, test results, performance, integrations or production readiness.

## Review boundaries

This documentation task permits local documentation and synthetic contract changes. It does not authorize Git operations, publishing, deployment, real receiving, external communication or changes to a central publication allowlist. Keep every Markdown link relative and use only `.md`, `.json` or `.svg` artifacts. See [delivery and validation](engineering/delivery-validation.en.md) for the proposed acceptance gate.
