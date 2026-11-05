# Engineering implementation guide — arkham

[English](index.en.md) · [Português (Brasil)](index.pt-BR.md) · [日本語](index.ja.md)

Proposed implementation documentation. No application, deployment, executed product checks or automatic agent calls are included. English documents are the complete design; Portuguese and Japanese documents are labeled actionable summaries with the same requirement IDs.

## Reading order

1. [Requirements](requirements.en.md)
2. [Module boundaries and state transitions](architecture.en.md)
3. [End-to-end rehearsal runbook](runbook.en.md)
4. [Implementation backlog and validation traceability](delivery-validation.en.md)

## Complete language map

- requirements: [en](requirements.en.md) · [pt-BR](requirements.pt-BR.md) · [ja](requirements.ja.md)
- architecture: [en](architecture.en.md) · [pt-BR](architecture.pt-BR.md) · [ja](architecture.ja.md)
- runbook: [en](runbook.en.md) · [pt-BR](runbook.pt-BR.md) · [ja](runbook.ja.md)
- delivery-validation: [en](delivery-validation.en.md) · [pt-BR](delivery-validation.pt-BR.md) · [ja](delivery-validation.ja.md)

## Scoped work and role specifications

[Repository work rules](../AGENTS.md). Roles are manually assigned responsibilities, not executable agents. Role specifications and contract keys are in English.

- [Session Scope Steward](../agents/session-scope-steward.md)
- [Catalog and Eligibility Analyst](../agents/catalog-eligibility-analyst.md)
- [Demo Submission Designer](../agents/demo-submission-designer.md)
- [Journey Verification Reviewer](../agents/journey-verification-reviewer.md)

## Contracts and synthetic examples

- [Draft 2020-12 schema](../contracts/onboarding-snapshot.schema.json)
- [Machine-readable validation cases](../contracts/validation-cases.json)
- [Valid synthetic fixture](../examples/snapshot.valid.json)
- [Invalid structure fixture](../examples/snapshot.invalid-schema.json)
- [Schema-valid, domain-invalid fixture](../examples/snapshot.invalid-semantic.json)

Invalid-semantic fixtures intentionally pass JSON Schema; their required domain failures are explained in the validation document. JSON shape alone does not prove runtime correctness.

## Existing public foundation

[README](../README.md) · [Architecture](../docs/architecture.en.md) · [Existing contracts](../docs/contracts.en.md) · [Decision record](../docs/decisions.en.md) · [Existing validation strategy](../docs/validation.en.md)
