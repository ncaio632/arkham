# Architecture

[README](../README.md)

## Processing flow

```text
Location input → validated session → base-scoped opportunity → eligibility → required document metadata → simulated receipt
```

## Invariants

1. Session establishes the base on the server; the opportunity endpoint reads that session.
2. A session cannot silently switch to another base; the reviewed handler returns 409.
3. Application submission rejects requests without a valid session and checks same-origin requests.
4. The reviewed application handler accepts document metadata in demo mode; real receiving is disabled with 503.
5. GPS proximity is a routing input, not proof of identity, residence or work eligibility.

## Implementation boundary

Reviewed prototype handlers exist in the private workspace. This public edition documents their contracts; it does not include the application or a production deployment.
