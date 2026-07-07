# API Readiness Workflow

Use this workflow before relying on an external API, provider SDK, or integration surface.

## Core Rule

Verify capability, permissions, rate limits, credential scope, and safety boundaries before building on an API.

## Workflow

1. Read official or primary API docs.
2. Identify required credentials by environment variable name only.
3. Classify the integration as read-only, write, admin, payment, broker, or destructive.
4. Run the smallest safe connectivity check.
5. Record available endpoints, missing endpoints, rate limits, and known SDK behavior.
6. Build a readiness report with evidence.
7. Keep live write or money-movement operations human-directed unless explicit policy allows automation.

## Readiness Report Shape

```text
Provider:
Credential variables:
Scope:
Endpoints tested:
Endpoints not tested:
Rate limits:
SDK/local cache behavior:
Safety boundary:
Validation command:
Result:
Last checked:
```

## Safety Boundary Examples

Read-only examples:

- account list
- positions
- balances
- historical orders
- market data
- public documents

Write or high-risk examples:

- placing orders
- modifying orders
- payments
- credential rotation
- account changes
- deleting remote data

## Checklist

- [ ] Primary docs checked.
- [ ] Credential variables documented without values.
- [ ] Scope classified.
- [ ] Readiness check run.
- [ ] Rate limits and local SDK caches noted.
- [ ] High-risk actions remain human-directed or explicitly allowed.
