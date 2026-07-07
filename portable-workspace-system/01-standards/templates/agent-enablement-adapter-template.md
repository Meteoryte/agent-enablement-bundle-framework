# Agent Enablement Adapter Template

Use this template when adopting the framework into a specific source application.

```markdown
# Agent Enablement Adapter

Source application: <project name>
Repo root: <path or repository URL>
Primary agent entrypoint: <path>
Task router: <path>
Docs hub: <path>
Command center: <path or none>
Standards folder: <path>
Validation command index: <path>
Design reference hub: <path or n/a>
Memory pattern: <none / project-local / workspace-local>

## Adopted Patterns

- Code naming:
- Document naming:
- Guidance asset naming:
- Source-of-truth protocol:
- Folder structure:
- Prompt-pack execution:
- Feature-gap closure:
- UI verification:
- Credential boundaries:
- Tool/MCP adapters:

## Source Mirrors Used As Examples

| Source mirror | Pattern adopted | Notes |
|---|---|---|
| `<path>` | `<pattern>` | `<notes>` |

## Project-Specific Surface Map

| Generic concept | Project-specific owner |
|---|---|
| agent entrypoint | `<path>` |
| task router | `<path>` |
| docs hub | `<path>` |
| architecture docs | `<path>` |
| development workflows | `<path>` |
| plans / continuation logs | `<path>` |
| reference library | `<path>` |
| validation scripts | `<path>` |

## Domain Keys

| Domain key | Owns |
|---|---|
| `<domain>` | `<responsibility>` |

## Required Keys

Document environment variable names only.

| Environment variable | Provider/subsystem | Purpose | Required? | Scope |
|---|---|---|---|---|
| `<ENV_VAR>` | `<provider>` | `<purpose>` | `<yes/no>` | `<read-only/write/local>` |

## Validation

- Naming:
- Links:
- Tests:
- UI:
- Secret scan:
- Manual checks:

## Intentionally Skipped

- `<pattern>` because `<reason>`
```
