# Portable Workspace Operating System

This document defines an app-agnostic and model-agnostic workspace framework. It is not a copy of one assistant's config, not a harness, and not a substitute for useful tools. It is a reusable coordination layer that makes a project or multi-project workspace legible to humans and AI agents.

The copyable neutral skeleton lives under [portable-workspace-system/](./portable-workspace-system/).

## Core Idea

A strong AI-friendly workspace has four jobs:

1. Route work to the right place.
2. Make project state observable.
3. Separate durable rules from run-specific outputs.
4. Give agents bounded workflows and clear validation interfaces.

The framework does this with numbered folders, a command center, standards libraries, local routers, stage contracts, optional memory, and tool-backed validation. It intentionally avoids product names, assistant names, and model-provider assumptions.

## Layer Map

| Layer | Portable purpose |
|---|---|
| Workspace identity | Explains what the workspace is, what it contains, and how agents should start. |
| Task router | Routes each request to a project, workflow, skill, standard, or command-center asset. |
| Command center | Central registry for projects, priorities, roadmap, decisions, and hub metadata. |
| Standards library | Durable engineering, naming, architecture, protocol, rule, workflow, and template assets. |
| Numbered work areas | Separates active projects, incubation, references, brands, tools, archive, backups, and idea audits. |
| Local folder contracts | Each major folder explains purpose, agent rules, status, and source files. |
| Stage workflows | Long work is split into stages with inputs, process, outputs, quality checks, and stop conditions. |
| Memory pattern | Optional markdown memory store shared by many agent surfaces. |
| Hub and health checks | Optional browser-accessible project selector plus scripts, MCP tools, or manual checks that validate registry and workspace health. |

## Neutral Folder Structure

Use this structure when a workspace has multiple projects, durable standards, and recurring AI-assisted workflows.

```text
workspace-root/
  agent-entrypoint.md or equivalent tool-specific entrypoint
  CONTEXT.md or equivalent task router
  README.md

  00-command-center/
    README.md
    project-registry.md
    priority-board.md
    roadmap.md
    decision-log.md
    next-actions.md
    workspace-hub.projects.json
    workspace-hub.project-schema.json

  01-standards/
    README.md
    engineering/
    rules/
    protocols/
    workflows/
    prompts/
    templates/
    skills/
    branding/

  02-active-projects/
  03-incubation/
  04-reference-library/
  05-brand-library/
  06-tools-and-extensions/
  07-archive/
  08-backups/
  09-idea-cloud-audit/

  _config/
    voice.md
    quality-standards.md
    preferences.md

  shared/
    audience.md
    glossary.md
    source-index.md

  skills/
    README.md

  workflows/
    README.md
    <workflow-name>/
      CONTEXT.md
      01-stage/
        CONTEXT.md
        output/

  memory/
    README.md
    INTEGRATIONS.md
    MEMORY.md

  scripts/
    workspace-health.*
    start-workspace-hub.*
    stop-workspace-hub.*
```

This is a pattern, not a mandate. Smaller repos can collapse layers. Larger workspaces can split standards or project areas further.

## Adoption Profiles

Choose the smallest profile that makes the workspace more observable.

| Profile | Use when | Keep | Skip at first |
|---|---|---|---|
| Single repo | One product or library needs better AI routing. | agent entrypoint, docs hub, plans, decisions, references, validation scripts. | numbered multi-project areas, hub, workspace-level memory. |
| Large repo | One product has many domains, docs, and long-running workflows. | command-center-lite, standards, workflows, local folder contracts, validation interfaces. | multi-project registry unless needed. |
| Multi-project workspace | Many projects, prototypes, references, and tools share one root. | full command center, numbered areas, standards library, project registry, weekly review. | browser hub until there are previewable projects. |
| Hub workspace | Many local apps or HTML prototypes need one preview surface. | full workspace plus hub registry, schema, start/stop scripts, health checks. | model-specific or editor-specific config in the portable layer. |

## Command Center Pattern

The command center prevents an unsearchable folder cloud. Its law is simple: if a project, major asset, decision, or initiative matters, register it.

Minimum command-center assets:

| Asset | Purpose |
|---|---|
| `project-registry.md` or `workspace-hub.projects.json` | Master list of projects, locations, owners, status, and runnable surfaces. |
| `priority-board.md` | What matters now, ranked by urgency and importance. |
| `roadmap.md` | Longer-term milestones and direction. |
| `decision-log.md` | Architecture, tooling, product, or workflow decisions with dates and reasons. |
| `next-actions.md` | Immediate work that an agent or human can pick up. |
| `weekly-review.md` | Recurring maintenance loop for stale projects, broken links, missing docs, and priorities. |

Why it works: agents can route before editing. Humans can audit what exists. Old work does not silently become current just because it is nearby.

Good command-center records are:

- dated
- owner-aware
- path-linked
- status-labeled
- explicit about next action
- clear about what is canonical and what is reference-only

## Standards Library Pattern

The standards library stores durable guidance by artifact type:

| Area | Purpose |
|---|---|
| `engineering/` | Architecture, module boundaries, naming, file creation, anti-monolith rules. |
| `rules/` | Normative constraints and rule hierarchy. |
| `protocols/` | Required step-by-step procedures for governed work. |
| `workflows/` | Repeatable multi-step sequences that combine protocols. |
| `prompts/` | Reusable prompts or prompt packs. |
| `templates/` | Copy/fill artifact shapes. |
| `skills/` | Invokable method playbooks with triggers and references. |
| `branding/` | Voice, visual identity, product naming, and design constraints. |

Why it works: the same concept always has the same home. A future agent can ask "is this a rule, protocol, workflow, template, or skill?" and route the artifact predictably.

Guidance assets should use responsibility names instead of vague labels. A future agent should be able to tell the domain, action, object, and artifact kind from the name.

## Local Folder Contract

Every major folder or module should carry a local contract:

| File | Purpose |
|---|---|
| `README.md` | What this folder is, why it exists, and what belongs here. |
| Local agent instructions | Local agent rules and boundaries. Optional if root rules are enough. |
| `STATUS.md` | Current state, owner, risks, and next actions. |
| Source files | The code, docs, assets, or data that the folder owns. |

Why it works: agents do not need to infer ownership from filenames alone. Local docs also reduce accidental edits in archive, backup, generated, or legacy folders.

## Workflow Stage Contract

Use stage contracts for work that should not happen in one giant prompt.

Each workflow has:

- root `CONTEXT.md` that lists stages and global rules
- numbered stage folders
- a local `CONTEXT.md` per stage
- local `output/` folder per stage

Each stage contract should define:

| Section | Required content |
|---|---|
| Purpose | What the stage accomplishes. |
| Inputs | Exact files, sections, or user-provided context it may read. |
| Process | Ordered actions. |
| Outputs | File path and format for stage artifacts. |
| Quality checks | What must be true before completion. |
| Stop conditions | When the agent must pause for human review. |

Why it works: context stays bounded, human-edited outputs become the source of truth for later stages, and agents can resume work without replaying the whole conversation.

The stage contract is also a prompt boundary. It tells an agent what to read, what not to read, what to produce, and when to stop.

## Agent-Surface And Model-Agnostic Rules

- Define roles by responsibility, not model name.
- Keep assistant-specific config out of the portable bundle.
- Use plain files, links, commands, schemas, and scripts as the interface.
- Document model providers only by capability and environment variable name.
- Treat hidden editor/assistant folders as local adapters, not portable source material.
- Hosted model use should be explicit when source code, private memory, or sensitive data may leave the machine.

## MCP Enhancement Layer

Many of these patterns can be improved by built-in MCP tools, connectors, or native LLM platform integrations. The framework should coordinate those tools, not replace them. Use MCPs to make the workspace more observable, not less portable.

Good MCP targets:

- search and refresh current docs
- inspect repository issues, pull requests, review comments, and CI
- query local files and project structure
- validate project registries and generated indexes
- capture browser screenshots and accessibility snapshots
- pull design-tool context
- sync external documents or tables into reference indexes
- scan portable docs for secret-like strings

Keep MCP behavior behind local adapters. The portable source of truth should remain plain Markdown, JSON, schemas, scripts, and documented commands. See [mcp-enhancement-notes.md](./portable-workspace-system/06-tools-and-extensions/mcp-enhancement-notes.md).

## Optional Hub Pattern

A hub is useful when the workspace contains many prototypes, local apps, HTML references, or previewable projects.

Portable hub contract:

- project registry is data, not hardcoded UI
- project ids are stable kebab-case
- paths are workspace-relative
- server commands are explicit
- dependency servers are separate from the app preview server
- file preview APIs reject traversal outside the project root
- health checks validate JSON, paths, scripts, syntax, and reachable previews

Why it works: agents and humans get one browser-accessible control surface, but the hub does not become the build system.

## Validation Interface Pattern

A workspace health checklist, script, MCP workflow, or manual review turns the framework into something testable.

Minimum checks:

- root entrypoint exists
- root router exists
- command-center registry exists
- registered paths stay inside the workspace
- registry IDs are stable and unique
- top-level Markdown links resolve
- JSON/YAML files parse
- workflow stages have `CONTEXT.md` and `output/`
- archive and backup folders are marked non-current
- secrets are not present in portable docs or memory

Optional checks:

- preview URLs respond
- hub schema validates the registry
- scripts pass syntax checks
- generated indexes are fresh
- UI projects have screenshot or visual smoke checks

Why it works: an agent can prove the workspace is still navigable before depending on it, while still using the best available local tools.

## Templates Included

The neutral skeleton includes:

- [agent-entrypoint-template.md](./portable-workspace-system/agent-entrypoint-template.md)
- [task-router-template.md](./portable-workspace-system/task-router-template.md)
- [local-folder-contract-template.md](./portable-workspace-system/local-folder-contract-template.md)
- [workspace-adoption-checklist.md](./portable-workspace-system/workspace-adoption-checklist.md)
- [project-registry-template.md](./portable-workspace-system/00-command-center/project-registry-template.md)
- [decision-log-template.md](./portable-workspace-system/00-command-center/decision-log-template.md)
- [priority-board-template.md](./portable-workspace-system/00-command-center/priority-board-template.md)
- [next-actions-template.md](./portable-workspace-system/00-command-center/next-actions-template.md)
- [weekly-review-template.md](./portable-workspace-system/00-command-center/weekly-review-template.md)
- [workspace-hub-projects-template.json](./portable-workspace-system/00-command-center/workspace-hub-projects-template.json)
- [workspace-hub-project-schema-template.json](./portable-workspace-system/00-command-center/workspace-hub-project-schema-template.json)
- [guidance-asset-types.md](./portable-workspace-system/01-standards/guidance-asset-types.md)
- [workspace-health-checklist.md](./portable-workspace-system/scripts/workspace-health-checklist.md)

## Adoption Sequence

1. Add the root agent entrypoint and task router.
2. Add `00-command-center/` with project registry, priorities, decisions, and next actions.
3. Add `01-standards/` with naming, architecture, rule, protocol, workflow, and template indexes.
4. Sort projects and references into numbered work areas.
5. Add local folder contracts to active areas first.
6. Add workflow stage contracts for recurring long-running work.
7. Add validation interfaces for the registry, links, naming, scripts, MCP tools, and important workflows.
8. Add memory only if cross-session context is actually needed.
9. Add a hub only if there are multiple previewable projects or demos.
10. Review stale folders weekly so the system remains trustworthy.

## Minimal Version For One Repo

For a normal single application repo, use the small version:

```text
repo-root/
  agent-entrypoint.md
  README.md
  docs/
    README.md
    document-naming-protocol.md
    development/
    architecture/
  plans/
    next-actions.md
    decision-log.md
  references/
  scripts/
  memory/        optional
```

The point is not the exact folder names. The point is observable state, bounded context, reusable standards, and validation.
