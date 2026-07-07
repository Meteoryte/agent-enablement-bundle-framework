# Source Of Truth Protocol

Use this protocol whenever a behavior, rule, weight, token, schema, prompt, or workflow appears in more than one place.

## Core Rule

Every important behavior should have one canonical owner and many consumers.

Do not tune behavior by patching downstream display code, copied examples, generated output, or screenshots. Change the source of truth, then validate every consumer that depends on it.

## Common SSOT Types

| SSOT type | Examples |
|---|---|
| Configuration module | weights, thresholds, flags, limits, routing tables |
| Schema | request/response contracts, event payloads, registry shape |
| Design token file | color, type, spacing, radius, motion |
| Protocol doc | required procedure for high-risk work |
| Workflow doc | repeatable sequence with inputs and validation |
| Registry | projects, tools, components, routes, widgets, data feeds |
| Fixture corpus | expected behavior for known cases |
| Prompt pack | staged instructions and acceptance criteria |

## Change Workflow

1. Identify the canonical owner.
2. Read the consumer map or coverage doc.
3. Edit the SSOT, not a downstream workaround.
4. Add or update fixtures when behavior changes.
5. Run the validation interface for the SSOT and affected consumers.
6. Update coverage, registry, or architecture docs if ownership changed.
7. State expected drift or behavior change in the final note.

## Consumer Map

For each important SSOT, keep a short map:

```text
SSOT:
Consumers:
Validation:
Known caveats:
Last verified:
```

Example:

```text
SSOT: market-news-score-weights
Consumers: score builder, row badge, summary report, regression fixtures
Validation: scoring regression and historical replay
Known caveat: replay may include calendar drift
```

## Drift Policy

If a consumer disagrees with the SSOT:

- fix the consumer if the SSOT is correct
- fix the SSOT if the rule itself is wrong
- update the consumer map if a new owner was introduced intentionally
- never leave two independent rule copies without a documented reason

## Fixture Rule

When a rule change matters, add a narrow fixture that proves the intended boundary. Good fixtures assert one clear decision, use time-stable inputs, and avoid whole-output snapshots unless the entire output is the contract.

## Checklist

- [ ] Is there one canonical owner?
- [ ] Are consumers listed or discoverable?
- [ ] Did the change happen at the owner, not the rendering layer?
- [ ] Did fixtures or examples change with the rule?
- [ ] Did validation run before claiming success?
- [ ] Did docs/coverage update if ownership changed?
