# Agent Entrypoint Template

Use this as the root agent instruction file for any assistant surface that reads project-local guidance. Rename it to the local convention your tool or repo expects.

## Workspace Identity

This workspace contains `<short description of project or multi-project workspace>`.

Primary purpose:

- `<purpose>`

Primary users:

- `<users>`

## Start Here

1. Read the task router: `CONTEXT.md`.
2. Read durable workspace rules in `_config/`.
3. Read local project or folder docs before editing.
4. Use the command center to find active projects, priorities, decisions, and next actions.
5. Run the relevant validation interface before calling work complete.

## Global Rules

- Do not edit archive or backup folders unless explicitly asked.
- Do not store secrets, API keys, tokens, OAuth material, or private credentials in docs or memory.
- Treat generated outputs as draft until approved or human-edited.
- Prefer local folder instructions over broad rules inside that folder's scope, unless they conflict with safety or command-center decisions.
- If required inputs are missing or contradict, stop and ask instead of inventing facts.
- Use absolute dates in durable docs and decisions.

## Source Of Truth

| Knowledge type | Location |
|---|---|
| Workspace identity | this file |
| Task routing | `CONTEXT.md` |
| Projects, priorities, decisions | `00-command-center/` |
| Standards, rules, protocols | `01-standards/` |
| Active project code/docs | `02-active-projects/` |
| Durable preferences | `_config/` |
| Cross-project knowledge | `shared/` |
| Stage workflows | `workflows/` |
| Optional memory | `memory/` |

## Validation

Before final response, report:

- files changed
- validation commands run
- checks skipped and why
- remaining risks or follow-ups
