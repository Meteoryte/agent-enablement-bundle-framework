# Rule Hierarchy And Safety Boundaries

This rulebook explains which instructions win and where agents must be conservative.

## Rule Hierarchy

Apply rules in this order:

1. Safety, legal, privacy, and credential boundaries.
2. Explicit current user request.
3. Repository or workspace entrypoint rules.
4. Local folder or workflow rules.
5. Standards, protocols, and templates.
6. Source mirrors and examples.
7. General agent judgment.

If two rules conflict, follow the higher rule and document the conflict.

## High-Risk Work

Treat these as high-risk:

- credential, token, OAuth, or secret handling
- payment, broker, order-routing, live-trade, or money movement workflows
- destructive filesystem or database changes
- authentication and authorization changes
- data deletion, retention, privacy, or export flows
- public publishing, package release, or repository upload
- migrations that alter persisted user data
- model/provider changes that send private source, memory, customer data, or regulated data out of the local environment

High-risk work needs explicit scope, source-of-truth checks, and validation evidence.

## Automation Boundary

Do not let an agent-controlled path perform irreversible external actions unless the repository has an explicit policy allowing it and a human-directed confirmation path.

Source-derived example:

```text
A finance workspace may allow analysis, simulation, backtesting, paper trading, and read-only account checks while banning AI-controlled live order placement.
```

The portable rule is broader:

```text
Analysis and recommendation are not the same as autonomous execution.
```

## Source Mirror Rule

Mirrored examples are evidence, not automatic policy. Promote a source-mirror rule into the portable standards layer or target repo rules before treating it as canonical.

## Stop Conditions

Pause for human review when:

- required inputs are missing or contradictory
- the task would expose or store secrets
- a change would make archived/reference material canonical
- a workflow would cross from read-only into write/execution mode
- validation cannot be run for a high-risk change
- public upload scope includes unknown private source material

## Checklist

- [ ] Did the higher-priority rule win?
- [ ] Is this high-risk work?
- [ ] Is external execution human-directed or explicitly allowed?
- [ ] Are source mirrors being used only as examples unless promoted?
- [ ] Are stop conditions handled before proceeding?
