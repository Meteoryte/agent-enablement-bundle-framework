# Tool And MCP Adapter Protocol

The framework coordinates useful tools. It does not replace them.

## Core Rule

Keep portable rules in plain files. Use tools, MCP servers, connectors, scripts, and hosted services as adapters that make the workspace more observable and verifiable.

## Adapter Map

For every tool integration, record:

| Field | Meaning |
|---|---|
| Capability | Search docs, inspect browser, query repo, validate registry, run screenshots, sync docs, etc. |
| Local adapter | Command, MCP server, connector, script, or manual process. |
| Required keys | Environment variable names only. |
| Source of truth | Which local file remains canonical. |
| Validation role | What evidence the tool can produce. |
| Fallback | What to do when the tool is unavailable. |

## Good Uses

Use tools to:

- search current public documentation
- inspect local files and project structure
- validate JSON/YAML/schema files
- run tests, lint, type checks, or naming audits
- capture screenshots and accessibility snapshots
- inspect repository issues, reviews, and CI
- fetch design context
- refresh reference indexes
- scan for secret-like strings before publishing

## Bad Uses

Do not use tools to:

- overwrite source-of-truth docs with generated guesses
- make private source public without export review
- bypass local ownership boundaries
- treat generated snippets as production-ready without integration
- replace validation with tool confidence

## MCP Notes

MCPs and native platform connectors can improve the framework by making context queryable and checks repeatable. Keep MCP-specific config in local adapters. The portable layer should still work as Markdown, JSON, schemas, scripts, and documented commands.

## Checklist

- [ ] Is the tool a capability adapter, not the canonical rule?
- [ ] Is the canonical local file named?
- [ ] Are required keys documented by environment variable only?
- [ ] Is there a fallback when the tool is unavailable?
- [ ] Is tool output validated before production use?
