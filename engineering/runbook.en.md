# End-to-end implementation rehearsal — arkham

This runbook specifies a future local synthetic rehearsal. No application command, deployed endpoint or executed product result is supplied by this repository. A builder must first implement adapters and a harness against the requirements. Do not point this workflow at real records or enable real receiving to demonstrate completion.

## Preparation

1. Choose a disposable fixture store and controlled clock. Seed `SYN-BASE-A` and `SYN-BASE-B`, each with a distinct opportunity, catalog revision 1 and an explicit synthetic routing result. Use no real coordinates from devices or operational base locations.
2. Configure the proposed rule fixture: answer `license_confirmed=true` yields eligible; false yields ineligible; absence yields unknown. This is a test rule, not a legal or operational qualification.
3. For base A, require exactly `identity` and `license` metadata categories. Configure the 10 MiB per-item demo limit, MIME allowlist and an explicit real-receiving-disabled gate.
4. Record build revision, fixture version, clock value, expected results and the execution environment in a sanitized evidence record. Keep proposed cases marked `not_run` until observed.

## Happy path

Start from no session and confirm opportunity discovery is refused. Send a synthetic location input through intake; make the fixture router select A. The returned server state must carry A and a revision. Select only A's open opportunity. Evaluate explicit synthetic answers, then supply both category entries with positive sizes within the limit and allowed MIME values. Fetch a server snapshot; expect `ready` and `eligible` with reasons, current rule/catalog versions and matching base codes.

Invoke simulated submission with the current expected revision and a new synthetic idempotency key from an allowed origin. Expect a simulated receipt and `simulation_only: true`; inspect the UI confirmation for the same wording. Retry the same key and payload after an artificial connection loss; expect the identical receipt. Read stored state to establish that exactly one simulated record exists. Do not infer success from a button click or an HTTP response without checking the state.

## Recovery and adversarial cases

Attempt to change the bound base to B and to select B's opportunity; both must fail without returning B's catalog or mutating A. Advance the controlled clock beyond session expiry and attempt each mutation; all require restart. Deny location permission and verify that the UI shows retry/unavailable rather than automatically routing to A.

Remove one required category, duplicate a category, exceed the size limit and change MIME to an unsupported value in separate requests. Expect 422 and no receipt. Change catalog or rules immediately before submission; expect 409 and renewed evaluation. Execute two matching submissions concurrently; require one receipt. Reuse a key with changed metadata; require conflict. Send the same valid input from a disallowed origin; expect 403 before mutation. Attempt real receiving; require 503 without any suggestion of stored files.

## Stop, rollback and evidence

Stop rehearsal on unexpected cross-base disclosure, real-receiving availability or personal data appearing in logs. Preserve sanitized error codes and fixture identifiers, disable the rehearsal adapter and discard the disposable store. Do not “fix” an expiry or conflict by editing session state manually.

For each case record requirement ID, input fixture, expected outcome, observed outcome, revision, time and verdict. Attach only synthetic snapshots and counts. Failed cases become backlog items; successful schema validation alone does not establish correct authorization or atomicity. A future live pilot requires separately approved policies, retention, security review and an actual application; this document grants no deployment authorization.


[Engineering index](index.en.md)
