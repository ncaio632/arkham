# Demo Submission Designer

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for A06, A07, A08. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Authorized session, current eligible result, required categories, metadata, expected revision and synthetic idempotency key.

## Outputs

Proposed atomic simulation boundary, validation failures, stable demo receipt semantics and real-receiving-disabled behavior. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Journey Verification Reviewer**. Provide the frozen revision, synthetic normalized payload fingerprint, expected duplicate behavior and evidence that no binary upload is part of this contract. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop on real receiving enabled, incomplete categories, stale eligibility, unapproved origin, unavailable atomicity or any request for a production receipt. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
