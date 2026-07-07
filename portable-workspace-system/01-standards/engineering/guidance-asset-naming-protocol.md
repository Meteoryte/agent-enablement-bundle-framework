# Guidance Asset Naming Protocol

Guidance assets are the files agents read to decide what to do. They need names that reveal their role before the file is opened.

## Asset Kinds

| Asset kind | Use when | Name pattern |
|---|---|---|
| Rule | A constraint that must be obeyed. | `<domain>-<object>-rules.md` |
| Protocol | A required procedure for governed work. | `<domain>-<object>-protocol.md` |
| Workflow | A repeatable multi-step sequence. | `<domain>-<verb>-<object>-workflow.md` |
| Canon | A durable source of truth for a concept. | `<domain>-<object>-canon.md` |
| Doctrine | A broad operating philosophy with review rules. | `<domain>-doctrine.md` |
| Runbook | Operational steps for a known task or incident. | `<domain>-<task>-runbook.md` |
| Checklist | A completion or review gate. | `<domain>-<task>-checklist.md` |
| Template | Copy/fill artifact shape. | `<domain>-<object>-template.md` |
| Prompt | Reusable model instruction. | `<domain>-<intent>-prompt.md` |
| Skill | Invokable method playbook with triggers. | `<domain>-<verb>-<object>-skill.md` |
| Eval case | A test case for a workflow, prompt, tool, or agent. | `<domain>-<behavior>-eval-case.json` |
| Schema | Structured data contract. | `<domain>-<object>-schema.json` |

## Name Formula

```text
<domain>-<verb-or-topic>-<object>[-<variant>]-<asset-kind>
```

Examples:

```text
document-rename-protocol.md
feature-gap-closure-workflow.md
credential-secret-boundary-protocol.md
workspace-health-checklist.md
agent-entrypoint-template.md
```

## Domain Rules

Use durable domain nouns:

```text
docs
workspace
agent
credential
validation
design-system
scoring
api
runtime
memory
```

Avoid private abbreviations unless the repo already treats them as stable search terms.

Allowed common technical acronyms include:

```text
api
ci
css
db
html
json
llm
mcp
rag
sdk
ui
ux
yaml
```

## Alias Policy

Imported, exported, or legacy assets may keep their original names for provenance. Add a small index or README that maps the original name to the portable concept.

Example:

```text
Original source mirror: sources/docs/development/prompt-pack-execution-protocol.md
Portable concept: prompt-pack-execution-workflow.md
```

## Ambiguity Test

Before accepting a guidance asset name, ask:

- Can an agent tell whether this is a rule, protocol, workflow, template, or reference?
- Can a human search for the domain and find every related asset?
- Would this name still make sense in six months?
- Does the name avoid `final`, `new`, `copy`, `misc`, `notes`, and `ultimate`?

## Checklist

- [ ] The artifact kind is named in the suffix.
- [ ] The domain is stable and searchable.
- [ ] The name explains action or topic without hype.
- [ ] Source-mirror aliases are documented when original names are preserved.
- [ ] The asset is linked from the nearest standards README or index.
