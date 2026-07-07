# Portable Workspace System Template

This is a model-agnostic skeleton for a multi-project workspace or a large single repo that needs durable AI-friendly routing.

Guide: [portable-workspace-operating-system.md](../portable-workspace-operating-system.md)

## Structure

```text
portable-workspace-system/
  agent-entrypoint-template.md
  task-router-template.md
  local-folder-contract-template.md
  workspace-adoption-checklist.md
  00-command-center/
  01-standards/
  02-active-projects/
  03-incubation/
  04-reference-library/
  05-brand-library/
  06-tools-and-extensions/
  07-archive/
  08-backups/
  09-idea-cloud-audit/
  _config/
  shared/
  skills/
  workflows/
  memory/
  scripts/
```

Each folder has a README explaining its role. Add local agent-instruction or status files only where the target project needs local instructions, status, or overrides.

Starter templates:

- [agent-entrypoint-template.md](./agent-entrypoint-template.md)
- [task-router-template.md](./task-router-template.md)
- [local-folder-contract-template.md](./local-folder-contract-template.md)
- [workspace-adoption-checklist.md](./workspace-adoption-checklist.md)
- [00-command-center/project-registry-template.md](./00-command-center/project-registry-template.md)
- [00-command-center/decision-log-template.md](./00-command-center/decision-log-template.md)
- [00-command-center/priority-board-template.md](./00-command-center/priority-board-template.md)
- [00-command-center/next-actions-template.md](./00-command-center/next-actions-template.md)
- [00-command-center/weekly-review-template.md](./00-command-center/weekly-review-template.md)
- [00-command-center/roadmap-template.md](./00-command-center/roadmap-template.md)
- [00-command-center/workspace-hub-projects-template.json](./00-command-center/workspace-hub-projects-template.json)
- [00-command-center/workspace-hub-project-schema-template.json](./00-command-center/workspace-hub-project-schema-template.json)
- [01-standards/README.md](./01-standards/README.md)
- [01-standards/guidance-asset-types.md](./01-standards/guidance-asset-types.md)
- [01-standards/engineering/code-naming-protocol.md](./01-standards/engineering/code-naming-protocol.md)
- [01-standards/engineering/document-naming-protocol.md](./01-standards/engineering/document-naming-protocol.md)
- [01-standards/engineering/guidance-asset-naming-protocol.md](./01-standards/engineering/guidance-asset-naming-protocol.md)
- [01-standards/engineering/folder-structure-protocol.md](./01-standards/engineering/folder-structure-protocol.md)
- [01-standards/engineering/source-of-truth-protocol.md](./01-standards/engineering/source-of-truth-protocol.md)
- [01-standards/rules/rule-hierarchy-and-safety-boundaries.md](./01-standards/rules/rule-hierarchy-and-safety-boundaries.md)
- [01-standards/protocols/credential-and-secret-boundary-protocol.md](./01-standards/protocols/credential-and-secret-boundary-protocol.md)
- [01-standards/protocols/public-bundle-export-protocol.md](./01-standards/protocols/public-bundle-export-protocol.md)
- [01-standards/protocols/tool-and-mcp-adapter-protocol.md](./01-standards/protocols/tool-and-mcp-adapter-protocol.md)
- [01-standards/protocols/validation-evidence-protocol.md](./01-standards/protocols/validation-evidence-protocol.md)
- [01-standards/protocols/memory-continuity-protocol.md](./01-standards/protocols/memory-continuity-protocol.md)
- [01-standards/protocols/audit-corpus-handling-protocol.md](./01-standards/protocols/audit-corpus-handling-protocol.md)
- [01-standards/workflows/prompt-pack-execution-workflow.md](./01-standards/workflows/prompt-pack-execution-workflow.md)
- [01-standards/workflows/feature-gap-closure-workflow.md](./01-standards/workflows/feature-gap-closure-workflow.md)
- [01-standards/workflows/ui-change-verification-workflow.md](./01-standards/workflows/ui-change-verification-workflow.md)
- [01-standards/workflows/reference-library-curation-workflow.md](./01-standards/workflows/reference-library-curation-workflow.md)
- [01-standards/workflows/api-readiness-workflow.md](./01-standards/workflows/api-readiness-workflow.md)
- [01-standards/templates/agent-enablement-adapter-template.md](./01-standards/templates/agent-enablement-adapter-template.md)
- [01-standards/templates/protocol-template.md](./01-standards/templates/protocol-template.md)
- [01-standards/templates/workflow-template.md](./01-standards/templates/workflow-template.md)
- [_config/voice-template.md](./_config/voice-template.md)
- [_config/quality-standards-template.md](./_config/quality-standards-template.md)
- [_config/preferences-template.md](./_config/preferences-template.md)
- [memory/MEMORY-template.md](./memory/MEMORY-template.md)
- [memory/INTEGRATIONS-template.md](./memory/INTEGRATIONS-template.md)
- [06-tools-and-extensions/mcp-enhancement-notes.md](./06-tools-and-extensions/mcp-enhancement-notes.md)
- [scripts/workspace-health-checklist.md](./scripts/workspace-health-checklist.md)
- [workflows/_workflow-template/CONTEXT.md](./workflows/_workflow-template/CONTEXT.md)
- [workflows/_workflow-template/01-stage/CONTEXT.md](./workflows/_workflow-template/01-stage/CONTEXT.md)

## Operating Rules

- Keep source-of-truth docs in predictable folders.
- Keep generated outputs separate from canonical inputs.
- Register active projects and major assets in the command center.
- Use stage contracts for long-running workflows.
- Keep assistant/editor-specific config outside this portable template.
- Do not store secrets in the workspace template or memory layer.
