# ADR 001 — Location-aware driver onboarding

[README](../README.md)

## Context

A mobile onboarding design that binds an opportunity to a server-side base and validates eligibility before simulating submission.

## Decision

Bind opportunity scope to the server session instead of relying only on hidden UI components.

## Consequences

Server-side scoping adds session lifecycle and expiry handling; it prevents the client from selecting an arbitrary operational table.

## Evidence boundary

Reviewed prototype handlers exist in the private workspace. This public edition documents their contracts; it does not include the application or a production deployment.
