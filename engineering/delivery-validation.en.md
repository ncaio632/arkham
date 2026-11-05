# Implementation backlog and validation — arkham

## Sequenced backlog

Each item is a proposed work package. Completion requires implementation plus observed evidence, not merely this document or a role's statement. Use the [role specifications](../agents/session-scope-steward.md) for ownership handoffs; they are manual responsibilities and do not launch agents.

| Order | Work package and dependency | Acceptance criteria |
| --- | --- | --- |
| B1 | Approve synthetic policies and define fixture catalog; no dependency | Written versions exist for routing, expiry, eligibility and document metadata. Unknown and denied inputs have distinct examples; policy owners identify unresolved production choices. |
| B2 | Build intake/session boundary after B1 | Invalid coordinates never create a session; base is immutable; expiry rejects reads/mutations; new-session flow explicitly revokes old scope. No raw location in audit output. |
| B3 | Build scoped catalog and evaluator after B2 | Every selection is checked against session base; rules return three states and reason codes; selecting another opportunity clears dependent readiness. |
| B4 | Build metadata checker and presenter after B3 | Missing, duplicate, oversized and unsupported categories fail; blocked reasons have accessible recovery text; browser refresh reads server state. No upload-storage claim appears. |
| B5 | Build atomic demo coordinator after B4 | Current revisions and origin checked at write boundary; concurrent retry produces one receipt; altered payload under same key conflicts; real receiving always fails closed. |
| B6 | Execute rehearsal and independent review after B5 | All trace rows have observed results or explicitly unresolved failures; sanitized evidence reviewed; documentation clearly separates synthetic demo from a deployable product. |

Do not use a broad “onboarding works” ticket: preserve these dependencies and failure conditions. Before coding, settle the policy gaps in [requirements](requirements.en.md). A builder may choose storage and UI technology, but may not weaken server-side scoping or the real-receiving gate.

## Requirements-to-validation traceability

All product checks in this table are **planned, not executed** in the public documentation package. Assign each a stable check ID when the harness exists; keep fixture and observed result separate.

| Requirement | Proposed verification | Required observation |
| --- | --- | --- |
| A01 | No session, expired session, route denied | Correct refusal, no catalog data and no new receipt. |
| A02 | Tamper base and opportunity reference, including concurrent calls | A remains bound; B data never returned. |
| A03 | Boundary coordinates, missing permission, zero/negative accuracy | Reject invalid inputs; preserve explicit unavailable state. |
| A04 | True, false, absent answer plus rule revision change | Three distinct decisions; unknown cannot become ready. |
| A05 | Close opportunity or increment catalog before submit | 409, renewed discovery and no simulated write. |
| A06 | Metadata boundary at 10 MiB and 10 MiB+1; missing/duplicate categories | Accept permitted complete set; reject every invalid variant before receipt creation. |
| A07 | Disallowed origin, stale revision, real mode request | 403/409/503 respectively, no mutation or real receipt. |
| A08 | Concurrent identical key; altered payload; second key on same selection | One stable receipt; altered payload conflicts; no duplicate application. |
| A09 | Inspect logs and errors from all above checks | Only coarse codes/references; no raw coordinates, answers or document content. |

## Contract fixtures and validation layers

[Valid snapshot](../examples/snapshot.valid.json) is structurally valid and represents a plausible synthetic simulated journey. [Invalid shape](../examples/snapshot.invalid-schema.json) exceeds the byte limit and must fail JSON Schema at `documents[0].size_bytes`. [Invalid semantics](../examples/snapshot.invalid-semantic.json) has an opportunity from base B in a session bound to A; it deliberately passes schema shape but must fail domain validation with `BASE_CONFLICT`.

Use a Draft 2020-12 validator against the [schema](../contracts/onboarding-snapshot.schema.json). Syntax checking JSON is weaker than schema validation. Schema validates fields and state-dependent presence, but cannot establish equality between nested base fields, current wall-clock expiry, required category coverage from an external catalog or actual server authorization. Explicitly test those in the coordinator. The fixed synthetic reference pattern is for public fixtures; it is not a prescribed production identifier or a security mechanism.

## Review record and exit gate

A future evidence entry must contain check ID, requirement ID, implementation revision, fixture version, environment, expected and observed outcomes, verdict and reviewer role. `not_run`, `pass`, `fail` and `blocked` must be explicit; do not convert an omitted observation into a pass. Attach only synthetic data and sanitized assertions.

The engineering exit gate is a reviewed synthetic implementation with no unresolved invariant failure. Production readiness remains undecided until routing accuracy, legal eligibility, retention, threat modeling, accessibility, hosting and recovery have owners and measured review evidence. Existing private-prototype descriptions do not transfer test results to this public specification.


[Engineering index](index.en.md)
