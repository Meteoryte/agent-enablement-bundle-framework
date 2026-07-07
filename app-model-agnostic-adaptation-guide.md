# App And Model Agnostic Adaptation Guide

This bundle is meant to travel. Treat it as a reusable agent-enablement pattern for any software project, not as a guide that requires one app, one assistant, or one model provider.

The copied source mirrors under `sources/` and `external-sources/` preserve original names, paths, and product language so their provenance stays clear. When you adapt the bundle elsewhere, translate those examples into the target project's language in a separate adapter note or live project doc instead of rewriting the mirrored evidence.

For the neutral workspace-system framework, read [portable-workspace-operating-system.md](./portable-workspace-operating-system.md) and inspect [portable-workspace-system/](./portable-workspace-system/).

For the concrete portable protocols, start at [portable-workspace-system/01-standards/README.md](./portable-workspace-system/01-standards/README.md). The source mirrors are allowed as examples when they are sanitized and the target project owner approves their use, but the standards folder is the copyable framework layer.

## Neutral Terms

Use these terms when porting the bundle:

| Term | Meaning |
|---|---|
| Source application | The project being made easier for agents to understand, edit, validate, and maintain. |
| Source mirror | A copied artifact kept for evidence and pattern reuse. Source mirrors may keep original app or tool names. |
| Agent surface | The assistant, IDE, CLI, chat UI, or automation tool reading the project. |
| Model provider | The LLM backend used by an agent surface. Examples include local models, hosted APIs, and IDE-bundled models. |
| Adapter doc | A small project-specific document that maps this bundle's generic patterns to the target repo. |
| Validation interface | A repeatable command, script, MCP tool, test, hook, eval, lint, screenshot loop, audit loop, or manual check that proves behavior. |

## Portability Rule

Keep the reusable layer generic and move project-specific details into adapters.

Use generic language in bundle-level docs:

- `source application`, not a fixed product name.
- `agent surface`, not a fixed assistant.
- `model provider`, not a fixed model family.
- `validation interface`, not a fixed test command unless the command is a source-mirror example.
- `project docs hub`, not a fixed docs path unless linking to a mirrored example.

Use original names only when they are provenance, source paths, examples, or compatibility details.

## Reusable Layers

These layers should remain app/model agnostic:

| Layer | Portable purpose |
|---|---|
| Agent entrypoint | Tells any agent how to start, which rules apply, and which work is forbidden or high-risk. |
| Project map | Routes an agent to source folders, docs hubs, architecture maps, and ownership boundaries. |
| Naming protocol | Keeps code, docs, logs, metrics, tests, and workflow artifacts searchable and responsibility-based. |
| Document location protocol | Defines where protocols, rules, workflows, prompts, templates, schemas, evals, and references live. |
| Workflow contracts | Breaks work into phases with required inputs, outputs, quality checks, and stop conditions. |
| Validation interfaces | Connects rules to executable checks, MCP tools, screenshot loops, audits, regressions, evals, or manual review. |
| Reference library | Makes external docs, UI libraries, APIs, and source references observable instead of hidden in chat memory. |
| Memory pattern | Provides optional cross-agent continuity through plain files and generated indexes. |
| Design reference layer | Gives UI agents visual targets, atomic examples, implementation workflow, and verification loops. |

## Adaptation Sequence

1. Identify the source application name, repo root, docs hub, main runtime, and primary user-facing surfaces.
2. Create or update the agent entrypoint for the target surface using the local project-instruction convention.
3. Map naming rules from the bundle into the target repo's naming protocol. Keep domain-flow-responsibility naming, but replace project-specific surface names.
4. Map document locations. Decide where protocols, rules, workflows, prompts, templates, schemas, eval cases, and design references belong in the target repo.
5. Map workflow contracts. For each recurring work type, define required inputs, process, outputs, quality checks, and stop conditions.
6. Map validation interfaces. Link every important rule to a command, MCP tool, test, screenshot loop, audit, or manual check.
7. Map reference libraries and MCP/tooling. Record API keys by environment variable name only. Never place secret values in docs.
8. Map memory only if the project needs cross-session or cross-tool continuity. Keep markdown canonical and generated indexes disposable.
9. For UI projects, map the design reference layer to the target design system, exported HTML references, screenshots, prototype suite, and implementation workflow.
10. Add a short adapter note that explains what was adopted, what was intentionally skipped, and which source mirrors are examples only.

Recommended first-copy standards:

- [code-naming-protocol.md](./portable-workspace-system/01-standards/engineering/code-naming-protocol.md)
- [document-naming-protocol.md](./portable-workspace-system/01-standards/engineering/document-naming-protocol.md)
- [guidance-asset-naming-protocol.md](./portable-workspace-system/01-standards/engineering/guidance-asset-naming-protocol.md)
- [folder-structure-protocol.md](./portable-workspace-system/01-standards/engineering/folder-structure-protocol.md)
- [source-of-truth-protocol.md](./portable-workspace-system/01-standards/engineering/source-of-truth-protocol.md)
- [rule-hierarchy-and-safety-boundaries.md](./portable-workspace-system/01-standards/rules/rule-hierarchy-and-safety-boundaries.md)
- [credential-and-secret-boundary-protocol.md](./portable-workspace-system/01-standards/protocols/credential-and-secret-boundary-protocol.md)
- [public-bundle-export-protocol.md](./portable-workspace-system/01-standards/protocols/public-bundle-export-protocol.md)
- [validation-evidence-protocol.md](./portable-workspace-system/01-standards/protocols/validation-evidence-protocol.md)
- [tool-and-mcp-adapter-protocol.md](./portable-workspace-system/01-standards/protocols/tool-and-mcp-adapter-protocol.md)
- [prompt-pack-execution-workflow.md](./portable-workspace-system/01-standards/workflows/prompt-pack-execution-workflow.md)
- [feature-gap-closure-workflow.md](./portable-workspace-system/01-standards/workflows/feature-gap-closure-workflow.md)
- [ui-change-verification-workflow.md](./portable-workspace-system/01-standards/workflows/ui-change-verification-workflow.md)

## Model-Agnostic Agent Roles

Define roles by responsibility, not by model name:

| Role | Responsibility |
|---|---|
| Planner | Reads context, detects constraints, sequences work, and identifies validation. |
| Builder | Edits code, docs, tests, configs, or assets inside ownership boundaries. |
| Reviewer | Looks for bugs, regressions, missing tests, security risk, and stale docs. |
| Researcher | Gathers current or niche external facts and records source links. |
| Designer | Uses design references, tokens, component systems, and visual verification loops. |
| Operator | Runs validation tools, audits, packaging checks, migrations, and release procedures. |

Any agent surface or model provider can fill these roles if it has the right context and tools.

## Provider-Safe Rules

- Do not store plaintext API keys, tokens, OAuth secrets, private prompts, or user secrets in the bundle.
- Document keys by environment variable name, provider, purpose, and setup link.
- Treat hosted-model use as opt-in when private memory, source code, customer data, or regulated data may be sent out of the machine.
- Keep local-model fallbacks possible when privacy matters.
- Do not depend on a model-specific feature unless there is an adapter or fallback for other agent surfaces.
- Prefer plain Markdown, JSON, YAML, HTML, and scripts over proprietary memory formats.
- For current facts, pricing, laws, library versions, APIs, or product recommendations, verify against primary/current sources before updating docs.

## Adapter Template

Use this shape when porting the bundle into another project:

```markdown
# Agent Enablement Adapter

Source application: <project name>
Repo root: <path or repo URL>
Primary agent entrypoint: <path>
Docs hub: <path>
Validation command index: <path>
Design reference hub: <path or n/a>
Memory pattern: <none / project-local / workspace-local>

## Adopted Patterns

- Naming protocol:
- Document location protocol:
- Workflow contracts:
- Validation interfaces:
- Reference libraries:
- Memory:
- Design references:

## Source Mirrors Used As Examples

- <path> - <why it is useful>

## Project-Specific Replacements

- Replace `<source-app-example>` with `<target-domain-name>`.
- Replace `<agent-surface-example>` with `<target-agent-surface>`.
- Replace `<model-provider-example>` with `<target-provider-or-local-model>`.

## Required Keys

| Environment variable | Provider | Purpose | Required? |
|---|---|---|---|
| `<ENV_VAR>` | `<provider>` | `<purpose>` | `<yes/no>` |

## Validation

- <command or manual check>
```

## Portability Checklist

- Bundle-level docs use neutral source-application and agent-surface language.
- Source mirrors keep original app and tool names only as provenance or examples.
- Source-derived examples are sanitized before public export.
- Every project-specific rule has an owning live doc in the target repo.
- Every important workflow names inputs, outputs, quality checks, and stop conditions.
- Every important rule has a validation interface or documented manual check.
- API keys are documented by variable name only.
- Memory is optional, markdown-first, and safe for the target privacy boundary.
- UI references are tied to a visual verification loop if the project has a frontend.
