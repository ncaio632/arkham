# Session Scope Steward

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for A01, A02, A03, A09. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Approved synthetic routing/expiry policies, location-input classes, server snapshot revision and a scoped catalog fixture.

## Outputs

A proposed intake/session interface, immutable-base and expiry invariants, error-code mapping, and sanitized refusal evidence. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Catalog and Eligibility Analyst**. Pass only server-bound base and policy revision; never forward raw coordinates or delegate base authority to the presenter. Request a new explicit session for a base change. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop when routing policy or expiry is undefined, scope can be changed by client input, cross-base data appears, or any real location enters fixtures. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
