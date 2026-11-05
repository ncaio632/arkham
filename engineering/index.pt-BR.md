# Guia de implementação de engenharia — arkham

[English](index.en.md) · [Português (Brasil)](index.pt-BR.md) · [日本語](index.ja.md)

Documentação proposta; sem aplicativo, implantação, verificações de produto executadas ou chamadas automáticas a agentes. Os documentos em português e japonês são resumos acionáveis; o inglês contém o desenho completo. IDs de requisitos e limites são comuns.

## Reading order

1. [Requisitos](requirements.pt-BR.md)
2. [Módulos e transições de estado](architecture.pt-BR.md)
3. [Roteiro ponta a ponta](runbook.pt-BR.md)
4. [Backlog e rastreabilidade de validação](delivery-validation.pt-BR.md)

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

[README](../README.md) · [Architecture](../docs/architecture.pt-BR.md) · [Existing contracts](../docs/contracts.pt-BR.md) · [Decision record](../docs/decisions.pt-BR.md) · [Existing validation strategy](../docs/validation.pt-BR.md)
