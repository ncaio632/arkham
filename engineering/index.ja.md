# エンジニアリング実装ガイド — arkham

[English](index.en.md) · [Português (Brasil)](index.pt-BR.md) · [日本語](index.ja.md)

提案仕様です。アプリ、デプロイ、実行済み製品検証、自動エージェント呼出しは含みません。英語版が完全仕様で、日本語・ポルトガル語版は同じ要件IDを使う実行可能な要約です。

## Reading order

1. [要件](requirements.ja.md)
2. [モジュールと状態遷移](architecture.ja.md)
3. [一貫手順](runbook.ja.md)
4. [バックログと検証対応](delivery-validation.ja.md)

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

[README](../README.md) · [Architecture](../docs/architecture.ja.md) · [Existing contracts](../docs/contracts.ja.md) · [Decision record](../docs/decisions.ja.md) · [Existing validation strategy](../docs/validation.ja.md)
