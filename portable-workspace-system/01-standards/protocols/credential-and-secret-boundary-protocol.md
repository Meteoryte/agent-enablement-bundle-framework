# Credential And Secret Boundary Protocol

This protocol keeps credentials, token caches, local runtime state, and documentation from being confused with each other.

## Core Rule

Document credentials by name, purpose, and setup path. Never store literal secret values in docs, prompts, memory, public bundles, screenshots, logs, or copied examples.

## Allowed In Docs

Safe:

```text
MARKET_DATA_API_KEY
BROKER_READONLY_CLIENT_ID
BROKER_READONLY_CLIENT_SECRET
HOSTED_MODEL_API_KEY
FIRECRAWL_API_KEY
```

Unsafe:

```text
real token values
session cookies
OAuth refresh tokens
private key blocks
copied .env contents
local token-cache file contents
screenshots showing keys
```

## Credential Map

For each credential, document:

| Field | Meaning |
|---|---|
| Environment variable | The variable or secure-store key name only. |
| Provider or subsystem | Who issues it or what local component owns it. |
| Purpose | What it enables. |
| Scope | Read-only, write, admin, local-only, or hosted. |
| Storage | Environment, OS keychain, app secure store, CI secret, or local-only cache. |
| Required? | Required, optional, development-only, or test-only. |
| Setup link | Current setup docs or provider page. |

## Boundary Examples

Good boundary:

```text
The app stores the market-data API key in a secure local store and passes it to the runtime during configuration. The key is not the same as the broker SDK token cache.
```

Good boundary:

```text
The broker integration is read-only. Token cache files created by the SDK are local runtime state and must stay ignored.
```

Bad boundary:

```text
Paste the token into this Markdown file so future agents can reuse it.
```

## Inspection Rules

When debugging credential state:

- inspect presence, provider, scope, status, and expiration
- redact or hash values before printing
- never echo full key values
- never copy local token files into bundles
- keep `.env`, `.env.local`, token caches, logs, and screenshots out of public exports

## Public Export Rules

Before publishing a bundle:

1. Exclude `.env`, local token files, OAuth caches, logs, databases, screenshots with secrets, memory dumps, and raw private source mirrors.
2. Scan for secret-like strings.
3. Replace literal examples with placeholders.
4. Keep API-key instructions as environment variable names only.
5. Document what was excluded and why.

## Checklist

- [ ] Are only variable names documented?
- [ ] Are token caches clearly separated from API keys?
- [ ] Are credential scopes labeled?
- [ ] Are local runtime artifacts ignored or excluded?
- [ ] Did a secret-like scan run before public export?
- [ ] Are setup instructions usable without revealing values?
