# Audit Corpus Handling Protocol

Use this protocol for append-only datasets that capture reports, model outputs, user feedback, analyzer decisions, replay inputs, or evaluation traces.

## Core Rule

Audit corpora are evidence. Do not mutate historical rows to make current behavior look better.

## Corpus Map

For each corpus, document:

| Field | Meaning |
|---|---|
| Path | Where the corpus lives. |
| Producer | What writes rows. |
| Consumer | What reads rows. |
| Row meaning | What one row represents. |
| Labels | What labels exist and what they do not mean. |
| Mutation policy | Append-only, generated, curated, or replaceable. |
| Replay command | How to use it for validation. |
| Privacy level | Public, internal, private, sensitive. |

## Append-Only Rule

If the corpus is historical evidence:

- append new rows
- do not edit old rows
- do not delete inconvenient rows
- create a corrected follow-up row or separate curated fixture when needed
- keep replay tools responsible for interpreting old schema versions

## Label Semantics

State what fields mean and what fields do not exist.

Example:

```text
reportMode=report_all means the user exported the row into the audit corpus. It does not by itself mean the row is correct or incorrect.
```

This prevents future agents from inventing labels such as `verdict`, `wasCorrect`, or `feedback` when the corpus does not contain them.

## Public Export Rule

Audit corpora should not be included in a public framework package unless they are synthetic, redacted, licensed for publication, and deliberately scoped.

## Checklist

- [ ] Corpus path and producer are documented.
- [ ] Labels are defined precisely.
- [ ] Mutation policy is explicit.
- [ ] Replay or validation command is linked.
- [ ] Privacy level is labeled.
- [ ] Public exports exclude private corpora.
