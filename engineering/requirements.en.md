# Requirements — arkham

This is a proposed implementation specification derived from the public [architecture](../docs/architecture.en.md) and [decision](../docs/decisions.en.md). Existing public notes describe reviewed private prototype handlers; this package neither inspects that prototype nor claims these proposed modules, persistence rules or checks already exist. The public repository contains documentation and synthetic fixtures, not an application.

## Outcome and boundary

A candidate discovers an opportunity for one server-selected base, understands eligibility, supplies required document metadata and receives an explicitly simulated receipt. A successful demo means that each decision can be explained and a cross-base request cannot change its scope. GPS is routing information, never evidence of identity, residence or permission to work. A production application, document storage, identity verification, job guarantee and external submission are outside this specification.

The following normative requirements describe the proposed target. `MUST` indicates a required acceptance condition; it does not assert current implementation.

| ID | Required behavior | Failure behavior |
| --- | --- | --- |
| A01 | Create or recover a server session before listing opportunities. Derive one `base_code` using a versioned routing policy. | Missing/expired session: 401; denied routing: 403; malformed location: 422. Return no opportunity data. |
| A02 | Keep the established base immutable within a session. Resolve all catalog queries using the stored base, never a client-supplied table or base. | Attempted base change: 409; explain that an explicit new-session flow is needed. |
| A03 | Validate finite latitude −90..90, longitude −180..180 and positive accuracy before routing. If permission is denied, offer an explicit unavailable/retry state. | Never silently select a default base or treat inaccurate coordinates as a confirmed location. |
| A04 | Evaluate a versioned eligibility rule set against explicit candidate answers; return `eligible`, `ineligible` or `unknown`, with reason codes. | Missing information stays unknown and blocks readiness; an unanswered boolean is not false. |
| A05 | Bind the selected opportunity and required document categories to the same base and catalog revision. Recheck availability and rules at submission. | Closed opportunity or changed revision: 409 and rediscovery; preserve no apparently successful submission. |
| A06 | Validate only synthetic document metadata in demo mode. Use a proposed demo limit of 10 MiB per item and MIME allowlist PDF/JPEG/PNG; require every category from the opportunity. | Unsupported MIME, missing category, duplicate category or invalid size: 422. No binary receipt or storage claim. |
| A07 | Require a valid same-origin request, live session, current eligible result and idempotency key for simulated submission. | Invalid origin: 403; expired session: 401; unmet prerequisites: 409. Real receiving stays disabled with 503. |
| A08 | Produce `simulation_only: true` and an opaque synthetic receipt reference. Retry of the same accepted key and identical payload returns the same receipt. | Same key with a different payload: 409; no second simulated application. |
| A09 | Expose coarse event and reason codes, revision and correlation reference without coordinates, document contents or candidate answers in logs. | Error responses identify a corrective action without echoing submitted personal content. |

## Product behavior

Show base, opportunity label, eligibility reasons and the word “simulation” at confirmation. A blocked or unknown result must offer a meaningful next action: correct missing answers, retry location permission, refresh the opportunity, or restart a session. Browser refresh recovers state only through the server; browser storage cannot authorize a step. Cancellation invalidates the demo session and removes its transient draft according to the future retention policy.

## Decisions still required

Before implementation, product and security owners must approve routing boundaries, minimum acceptable location accuracy, session lifetime, required categories, eligibility rule content and retention periods. The 10 MiB limit and MIME list above are design defaults for a synthetic demo, not validated operational policy. Store policy revisions with evaluations so a later change cannot silently reinterpret an earlier answer. No stack, database, map provider or identity service is selected here.


[Engineering index](index.en.md)
