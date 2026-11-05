# Journey Verification Reviewer

A role specification for manually assigned engineering work. It is not an executable agent and does not trigger model calls, background tasks or tool access.

## Scope

Own the proposed design and review obligations for A01–A09. Read [requirements](../engineering/requirements.en.md), [architecture](../engineering/architecture.en.md) and [validation](../engineering/delivery-validation.en.md). Use only public specifications and synthetic inputs; do not infer access to a private prototype.

## Inputs

Requirements, proposed module contracts, synthetic fixtures and observed rehearsal records if they exist.

## Outputs

Traceability review, accessible recovery-copy findings and an evidence report that labels every unexecuted check not_run. Label design proposals, unresolved policies and actually observed evidence separately. Preserve stable requirement IDs and contract versions.

## Handoff

Next role: **Session Scope Steward**. Return a requirement-specific defect and minimal synthetic reproduction to the owning role. Distinguish documentation/schema checks from product execution. The receiver must acknowledge the revision and unresolved blockers before proceeding; a handoff alone does not satisfy an acceptance criterion.

## Stop conditions

Stop publication review for real data, fabricated pass claims, a missing requirement owner or unresolved scope leak. Do not authorize deployment or real submission. Return a concise blocker, the affected requirement and the smallest safe synthetic reproduction. Never fabricate evidence to complete a handoff. See [engineering index](../engineering/index.en.md) for all roles.
