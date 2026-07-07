# 01 Standards

Purpose: durable rules, protocols, workflows, templates, prompts, skills, and engineering standards.

This folder is the portable standards library. Source mirrors may keep original project names for provenance, but reusable standards should live here in app-agnostic form.

## Folders

| Folder | Purpose |
|---|---|
| [engineering/](./engineering/) | Naming, folder structure, source-of-truth, and code/document organization standards. |
| [rules/](./rules/) | Rule hierarchy, safety boundaries, and non-negotiable constraints. |
| [protocols/](./protocols/) | Required procedures for governed work. |
| [workflows/](./workflows/) | Repeatable multi-step work loops. |
| [templates/](./templates/) | Copy/fill shapes for adapters, protocols, and workflows. |
| `prompts/` | Reusable prompt assets when adopted by a target project. |
| `skills/` | Invokable method playbooks when adopted by a target project. |
| `branding/` | Voice, visual identity, product naming, and design constraints when needed. |

## Engineering Standards

- [code-naming-protocol.md](./engineering/code-naming-protocol.md) - domain-flow-responsibility naming for code, logs, tests, metrics, and fixtures.
- [document-naming-protocol.md](./engineering/document-naming-protocol.md) - kebab-case document naming, document kinds, canonical locations, and rename workflow.
- [guidance-asset-naming-protocol.md](./engineering/guidance-asset-naming-protocol.md) - naming rules for rules, protocols, workflows, prompts, templates, skills, schemas, and evals.
- [folder-structure-protocol.md](./engineering/folder-structure-protocol.md) - currentness labels, folder contracts, generated output, references, archives, and backups.
- [source-of-truth-protocol.md](./engineering/source-of-truth-protocol.md) - SSOT ownership, consumer maps, fixture changes, replay, and drift handling.
- [guidance-asset-types.md](./guidance-asset-types.md) - quick map for choosing the right guidance artifact type.

## Rules

- [rule-hierarchy-and-safety-boundaries.md](./rules/rule-hierarchy-and-safety-boundaries.md) - instruction precedence, high-risk work, automation boundaries, and stop conditions.

## Protocols

- [credential-and-secret-boundary-protocol.md](./protocols/credential-and-secret-boundary-protocol.md) - credential maps, token-cache boundaries, inspection rules, and safe public-export handling.
- [public-bundle-export-protocol.md](./protocols/public-bundle-export-protocol.md) - staging, scanning, sanitizing, and publishing a reusable framework package.
- [tool-and-mcp-adapter-protocol.md](./protocols/tool-and-mcp-adapter-protocol.md) - using MCPs, connectors, scripts, and tools as adapters instead of source-of-truth replacements.
- [validation-evidence-protocol.md](./protocols/validation-evidence-protocol.md) - validation interfaces, evidence shape, fixture/replay pattern, UI checks, and skip policy.
- [memory-continuity-protocol.md](./protocols/memory-continuity-protocol.md) - markdown-first memory, privacy boundaries, and update rules.
- [audit-corpus-handling-protocol.md](./protocols/audit-corpus-handling-protocol.md) - append-only corpora, label semantics, replay maps, and public-export exclusion.

## Workflows

- [prompt-pack-execution-workflow.md](./workflows/prompt-pack-execution-workflow.md) - digest staged prompt packs, execute in order, validate slices, and promote reusable rules.
- [feature-gap-closure-workflow.md](./workflows/feature-gap-closure-workflow.md) - maintain honest feature gap state and close gaps with evidence.
- [ui-change-verification-workflow.md](./workflows/ui-change-verification-workflow.md) - visual verification loop for UI-facing work.
- [reference-library-curation-workflow.md](./workflows/reference-library-curation-workflow.md) - add libraries, docs, examples, and UI references with source/cost/license/key metadata.
- [api-readiness-workflow.md](./workflows/api-readiness-workflow.md) - verify external API capability, scope, rate limits, and safety boundaries.

## Templates

- [agent-enablement-adapter-template.md](./templates/agent-enablement-adapter-template.md) - map this framework into a target project.
- [protocol-template.md](./templates/protocol-template.md) - write a governed-work protocol.
- [workflow-template.md](./templates/workflow-template.md) - write a repeatable workflow.

Use this folder for guidance that should outlive a single task or chat session.
