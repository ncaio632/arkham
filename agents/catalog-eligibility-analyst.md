# Catalog and Eligibility Analyst

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for A04, A05. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Server session base/revision, versioned synthetic catalog, rule definitions and explicit answer states.

## Outputs

Base-scoped opportunity selection, tri-state evaluation with stable reasons, required categories and versions. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Demo Submission Designer**. Handoff includes unknowns and exact rule/catalog revisions. Mark readiness false until all prerequisites are established; selecting another opportunity invalidates dependent results. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop on a missing rule, contradictory policy, catalog mismatch or request to infer eligibility from GPS. Do not convert absent answers into false or eligible. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
