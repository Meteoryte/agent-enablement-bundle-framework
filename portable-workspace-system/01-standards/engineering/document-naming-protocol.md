# Document Naming Protocol

Documents are part of the agent interface. Their names should be predictable, searchable, and stable.

## Core Shape

Use lowercase kebab-case:

```text
<domain>-<topic-or-flow>-<document-kind>.md
```

Examples:

```text
scoring-update-protocol.md
feature-gap-closure-workflow.md
credential-boundary-protocol.md
design-system-implementation-workflow.md
```

## Document Kinds

Prefer one of these suffixes when it fits:

```text
protocol
workflow
rule
rules
canon
doctrine
guide
reference
manual
runbook
playbook
checklist
catalog
map
coverage
report
audit
status
plan
spec
transcript
template
schema
```

Use the smallest accurate kind. A one-time finding is a `report` or `audit`, not a `protocol`. A required procedure is a `protocol`; a repeatable multi-step sequence is a `workflow`.

## Dates

Use dates only when the document is intentionally historical, event-bound, or a dated snapshot.

```text
runtime-inspection-2026-04-27.md
api-readiness-report-2026-07-06.md
2026-07-06-product-redesign-spec.md
```

Current canonical docs should not need dates:

```text
scoring-update-protocol.md
document-naming-protocol.md
project-structure-map.md
```

## Avoid

Avoid:

```text
ALL_CAPS.md
snake_case.md
spaces in names.md
misc-notes.md
final-final.md
ultimate-anything.md
new-doc.md
updated-copy.md
```

Replace hype or chronology with responsibility:

```text
ui-doctrine.md
backend-doctrine.md
prompt-pack-execution-workflow.md
```

## Canonical Locations

Use the owning folder, not whichever folder is open.

| Location | Belongs there |
|---|---|
| root | entrypoints, project README, license, changelog, compact agent rules |
| `docs/architecture/` | runtime architecture, system behavior, pipeline maps, durable technical protocols |
| `docs/development/` | engineering workflows, implementation runbooks, acceptance gates, prompt-pack process |
| `docs/design-system/` | visual standards, UI workflow, screenshots, design references |
| `docs/api/` | API contracts, provider readiness, endpoint references |
| `docs/research/` | source investigations and external reference notes |
| `docs/user/` | user-facing manuals and operating guides |
| `plans/` | active plans, continuation logs, backlog, dated task state |
| `references/` | non-canonical examples, third-party notes, copied inspiration |
| `01-standards/` | reusable rules, protocols, workflows, templates, skills, prompts |

When a document spans areas, place it where the reader will act on it.

## Source Mirrors

If a bundle mirrors source files, preserve the original relative path under the mirror. Do not rename copied evidence to make it prettier; add a portable summary next to it instead.

Example:

```text
sources/docs/development/prompt-pack-execution-protocol.md
```

The mirror proves provenance. The portable standards folder explains the reusable pattern.

## Rename Protocol

When renaming a document:

1. Choose the new name from `<domain>-<topic>-<kind>.md`.
2. Move the file.
3. Update Markdown links, plain path mentions, docs hubs, agent entrypoints, scripts, indexes, and bundle manifests.
4. If the old path was user-facing, add a migration note in the relevant hub.
5. Refresh mirrors when the bundle is in scope.
6. Run the naming and link validation interfaces.

## Checklist

- [ ] Is the file lowercase kebab-case?
- [ ] Does the name include a stable domain or topic?
- [ ] Does the suffix describe the document kind?
- [ ] Is the document in the owning folder?
- [ ] Are historical/exported/source-mirror names left alone unless intentionally migrated?
- [ ] Are every link and path mention updated?
- [ ] Did the naming and link checks run?
