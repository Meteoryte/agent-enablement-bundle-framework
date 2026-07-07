# Task Router Template

Use this as `CONTEXT.md` or the equivalent root task router.

## Route By Task Type

| Task type | First place to read | Notes |
|---|---|---|
| Work on an active project | `00-command-center/project-registry.md`, then the project folder | Project-local docs own local scope. |
| Create or update standards | `01-standards/README.md` | Decide whether the artifact is a rule, protocol, workflow, template, skill, prompt, or reference. |
| Create or rename code/docs | `01-standards/engineering/` | Follow code, document, and guidance-asset naming protocols. |
| Change shared behavior or configuration | `01-standards/engineering/source-of-truth-protocol.md` | Edit the canonical owner and validate consumers. |
| Handle credentials or public export | `01-standards/protocols/credential-and-secret-boundary-protocol.md`, then `01-standards/protocols/public-bundle-export-protocol.md` | Use variable names only and scan staged exports. |
| Prove work is complete | `01-standards/protocols/validation-evidence-protocol.md` | Run the relevant validation interface or explain skipped checks. |
| Produce a staged deliverable | `workflows/<workflow>/CONTEXT.md` | Follow stage contracts and output folders. |
| Research or summarize | relevant skill plus `shared/source-index.md` | Separate facts, interpretations, and open questions. |
| Update priorities or roadmap | `00-command-center/` | Record date and reason. |
| Archive or restore work | `07-archive/` or `08-backups/` only with explicit request | Update command-center registry. |
| Look up voice, preferences, quality bar | `_config/` | Keep durable preferences concise. |
| Use memory | `memory/MEMORY.md` | Optional; read only relevant memory files. |

## Loading Rules

- Load only the current task's required docs and explicitly named inputs.
- Prefer precise sections over whole large files.
- Later workflow stages may read earlier stage outputs; earlier stages should not read later outputs.
- Do not treat references, archives, backups, or generated outputs as canonical unless a command-center decision says so.

## Stop Conditions

Stop and ask for human review when:

- required inputs are missing or contradictory
- a task would overwrite human-edited output
- a task crosses outside the current workflow scope
- a change requires credentials or secrets that are not available through safe local configuration
- a decision would make archived or reference material canonical
