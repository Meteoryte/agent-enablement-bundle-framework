# Workspace Adoption Checklist

Use this checklist when applying the portable workspace system to a new repo or multi-project workspace.

## Phase 1: Inventory

- Identify the workspace root.
- Identify active projects, references, tools, archives, backups, and experiments.
- Identify existing agent instruction files.
- Identify existing docs hubs, plans, decision logs, and validation commands.
- Identify where secrets currently live and confirm they will not be copied into docs or memory.

## Phase 2: Routing

- Add or update the root agent entrypoint.
- Add or update the root task router.
- Create `00-command-center/`.
- Add project registry, next actions, priority board, and decision log.
- Register all active projects and major reference assets.

## Phase 3: Standards

- Create `01-standards/`.
- Add the standards index: `01-standards/README.md`.
- Add code naming, document naming, and guidance-asset naming protocols.
- Add folder-structure and source-of-truth protocols.
- Add rule hierarchy and safety boundaries.
- Add credential/secret boundary, public export, tool/MCP adapter, validation evidence, memory continuity, and audit-corpus protocols.
- Add prompt-pack execution, feature-gap closure, UI verification, reference-library curation, and API-readiness workflows as relevant.
- Add protocol, workflow, prompt, template, and skill indexes as needed.

## Phase 4: Structure

- Move or map active projects into the active-projects area.
- Move or map experiments into incubation.
- Move or map references into the reference library.
- Mark archives and backups clearly.
- Add local folder contracts to active areas first.

## Phase 5: Workflows

- Define recurring workflows that need stages.
- Create `CONTEXT.md` for each workflow.
- Create numbered stage folders with stage contracts.
- Add output folders and source-of-truth rules.

## Phase 6: Validation

- Add a workspace health checklist.
- Add link checks for docs.
- Add registry checks for required fields.
- Add naming checks where useful.
- Add project-specific build/test/screenshot checks.
- Add secret-like scanning before public export.
- Document skipped validation and why.

## Phase 7: Optional Layers

- Add memory only when durable cross-session context is needed.
- Add a hub only when multiple previewable projects need one control surface.
- Add generated indexes only when manual navigation becomes too slow.

## Done Criteria

- A new agent can find the right project without asking.
- Active work is registered and prioritized.
- Durable rules are separate from generated outputs.
- Long-running work has stage contracts.
- Validation is named and repeatable.
- Secrets are excluded.
