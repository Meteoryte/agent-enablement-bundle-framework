# Public Bundle Export Protocol

Use this protocol before publishing an agent-enablement bundle, framework, template, or extracted reference package.

## Core Rule

Publish reusable patterns, portable templates, safe examples, and sanitized source-derived explanations. Do not publish raw private source mirrors, secrets, runtime state, user data, logs, local memory, or credential caches unless the owner explicitly scopes them and they pass review.

## Publishable

Usually safe after review:

- portable framework docs
- templates
- sanitized protocols and workflows
- sanitized examples with placeholders
- generated indexes without secrets
- public-facing README files
- schemas with fake sample values
- design-process descriptions without private assets

## Exclude Or Sanitize

Exclude by default:

- `.env`, `.env.local`, local credential stores, token caches
- OAuth/session files, cookies, private keys
- logs, databases, local memory dumps, audit corpora with user data
- raw copied repositories or source mirrors with unknown license or privacy status
- screenshots that may reveal tokens, customer data, account data, private paths, or unreleased product details
- generated output folders unless intentionally curated
- hidden editor or assistant config folders unless they are deliberately part of the public template

## Review Workflow

1. Define the export scope.
2. Build a staging folder separate from the live workspace.
3. Copy only the intended portable files.
4. Scan for secret-like strings.
5. Scan for private product names if the package is meant to be generic.
6. Check links inside the staged package.
7. Parse structured files such as JSON and YAML.
8. Review README claims against the staged contents.
9. Commit and publish from the staging folder.
10. Record what was excluded and why.

## Safe Example Rule

Examples are allowed when they teach the pattern without exposing live private material.

Good:

```text
MARKET_DATA_API_KEY=<set in local environment>
```

Bad:

```text
MARKET_DATA_API_KEY=<real key value>
```

Good:

```text
A market-data project kept score weights in a dedicated module and verified changes with fixtures and replay.
```

Bad:

```text
Copy the full private scoring corpus into the public framework repo.
```

## Checklist

- [ ] Export scope is explicit.
- [ ] Staging folder contains only intended files.
- [ ] Secret-like scan passed.
- [ ] Link check passed.
- [ ] Structured files parse.
- [ ] Examples are sanitized.
- [ ] README does not claim excluded files are present.
- [ ] Exclusion rationale is documented.
