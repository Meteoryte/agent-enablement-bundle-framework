# Guidance Asset Types

Use this map to decide where an AI-facing asset belongs.

| Asset type | Purpose | Canonical location | Name pattern |
|---|---|---|---|
| Skill | Invokable method playbook with triggers and procedure. | `01-standards/skills/` or `skills/` | `<domain>-<verb>-<object>-skill.md` |
| Workflow | Repeatable end-to-end sequence. | `01-standards/workflows/` or `workflows/` | `<domain>-<verb>-<object>-workflow.md` |
| Protocol | Required procedure for governed work. | `01-standards/protocols/` | `<domain>-<object>-protocol.md` |
| Rule | Normative constraint or law. | `01-standards/rules/` | `<domain>-<object>-rules.md` |
| Prompt | Reusable model instruction. | `01-standards/prompts/` | `<domain>-<intent>-prompt.md` |
| Template | Copy/fill artifact shape. | `01-standards/templates/` | `<domain>-<object>-template.md` |
| Reference | Supporting knowledge, not executable instruction. | `04-reference-library/` | `<domain>-<object>-reference.md` |
| Tool contract | Contract for a callable tool or script. | project docs or `01-standards/templates/` | `<domain>-<tool>-tool-contract.md` |
| Agent spec | Runtime and behavior spec for an agent role. | project docs or `01-standards/templates/` | `<domain>-<agent>-agent-spec.md` |
| Eval case | Test case for a prompt, workflow, tool, or agent. | project eval folder | `<domain>-<behavior>-eval-case.json` |
| Schema | Structured data or output contract. | project schema folder | `<domain>-<object>-schema.json` |

Name formula:

```text
<domain>-<verb>-<object>[-<variant>][-<artifact-kind>]
```

Avoid vague names such as `helper`, `final`, `new`, `mode`, `misc`, `manual`, or private acronyms that are not searchable.
