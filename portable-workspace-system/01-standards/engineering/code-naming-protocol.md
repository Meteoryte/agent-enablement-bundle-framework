# Code Naming Protocol

Use names that tell an agent where a thing belongs, which flow it participates in, and what responsibility it owns.

## Core Shape

```text
<domain><Flow><Responsibility><Kind?>
```

Examples:

```text
orderCheckoutValidateRequest
orderCheckoutPersistOrder
MarketNewsScoreWeights
readerRuntimeObserveFrame
```

Use the same stable flow key across files, functions, types, tests, logs, metrics, fixtures, and docs.

## Domain And Flow Keys

A domain is the owning bounded context. A flow is the user or system sequence inside that domain.

Examples:

| Domain | Flow | Stable key |
|---|---|---|
| `order` | checkout | `orderCheckout` / `order.checkout` |
| `marketNews` | scoring | `marketNewsScore` / `market_news.score` |
| `readerRuntime` | observe | `readerRuntimeObserve` / `reader_runtime.observe` |
| `designSystem` | migration | `designSystemMigration` / `design_system.migration` |

Do not use broad words such as `ai`, `data`, `app`, `core`, or `system` as the whole domain when the project has more precise surfaces. If a user asks for work on an ambiguous surface, identify the surface before editing.

## Responsibility Names

Name functions by responsibility, not by the entire call chain.

Good:

```text
orderCheckoutValidateRequest
orderCheckoutAuthorizeUser
orderCheckoutCalculateTotals
orderCheckoutBuildResponse
```

Avoid:

```text
orderCheckoutValidateAuthorizeLoadCalculatePersistReturn
```

Keep the sequence in an orchestration function, flow map, workflow doc, or test.

## File Names

Use the local language convention while preserving the same domain-flow-responsibility model.

TypeScript-style examples:

```text
order.checkout.endpoint.ts
order.checkout.validate-request.ts
market-news.score.weights.ts
reader-runtime.observe.contracts.ts
```

Python-style examples:

```text
order_checkout_endpoint.py
order_checkout_validate_request.py
market_news_score_weights.py
reader_runtime_observe_contracts.py
```

Documents use the document naming protocol instead of source-code file casing.

## Avoid Vague Names

Avoid new names built around:

```text
helper
utils
manager
processor
handler
service
data
result
payload
thing
temp
final
new
misc
```

Some frameworks require words such as `service` or `handler`. When required, add the domain and responsibility:

```text
orderCheckoutPaymentService
webhookSignatureVerifyHandler
```

## Public Contract Rule

Do not rename public or persisted contracts for naming-only reasons unless the migration is explicit and verified.

Protected contract examples:

- routes and URL paths
- public API fields
- persisted storage keys
- database tables and columns
- environment variables
- message channels and event names
- exported package APIs
- fixture IDs and snapshot IDs

Legacy names are allowed to remain. When touching legacy code, improve the edited surface without doing unrelated mass renames.

## Logs And Metrics

Use stable event names:

```text
order.checkout.started
order.checkout.completed
market_news.score.regression_failed
reader_runtime.observe.frame_captured
```

Keep high-cardinality values out of metric names. Put request IDs, user IDs, symbols, filenames, or record IDs in structured fields only when the observability store is designed for them.

## Checklist

- [ ] Does the name expose domain, flow, and responsibility?
- [ ] Can the flow be searched by one stable key?
- [ ] Are vague helper-style names avoided?
- [ ] Are public contracts left stable or migrated intentionally?
- [ ] Do tests, logs, metrics, fixtures, and docs use the same flow key?
- [ ] Are legacy names improved only where the work actually touches them?
