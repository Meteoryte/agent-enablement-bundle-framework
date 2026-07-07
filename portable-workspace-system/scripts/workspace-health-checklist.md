# Workspace Health Checklist

Use this as a script spec or manual checklist.

## Required Checks

- Root agent entrypoint exists.
- Root task router exists.
- Command center exists.
- Project registry exists and required fields are populated.
- Priority board, next actions, roadmap, and decision log exist.
- Standards folder exists and has guidance asset type rules.
- Standards folder includes code naming, document naming, guidance-asset naming, folder-structure, and source-of-truth protocols.
- Standards folder includes rule hierarchy, credential/secret boundary, public export, tool/MCP adapter, validation evidence, memory continuity, and audit-corpus protocols.
- Standards folder includes prompt-pack execution, feature-gap closure, UI verification, reference-library curation, and API-readiness workflows when relevant to the workspace.
- Active projects have README files.
- Archive and backup folders are clearly marked as non-current.
- Workflow folders have root and stage `CONTEXT.md` files.
- Stage output folders exist where stages require them.
- Memory folder, if present, has README and no secrets.
- Links in top-level docs resolve.
- JSON/YAML files parse.
- Script files pass syntax checks where practical.
- Public export staging, if present, has passed secret-like scan and link check.

## Optional Checks

- Project preview URLs respond.
- Local hub registry validates against schema.
- Screenshots can be captured for UI projects.
- Generated indexes are up to date.
- All command-center projects were reviewed within the target cadence.

## Output Shape

```text
ok - <check name>
not ok - <check name>: <reason>
```

The health check should fail loudly when registry paths point outside the workspace, hidden secrets appear in portable docs, or generated files are mistaken for source of truth.
