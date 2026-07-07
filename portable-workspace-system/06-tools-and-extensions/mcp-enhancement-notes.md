# MCP Enhancement Notes

Many parts of this workspace framework can be improved by using built-in MCP tools, connectors, or native agent integrations when an LLM environment provides them.

The framework is not a replacement for those tools. Keep the portable workspace model tool-agnostic, then let local adapters use MCP capabilities to make the system faster and more observable.

## Useful MCP Enhancement Areas

| Workspace layer | MCP or connector improvement |
|---|---|
| Command center | Read project registries, update issue/PR links, inspect repo metadata, and sync priority state from external systems. |
| Project registry | Validate paths, detect runnable projects, query package manifests, and refresh status fields automatically. |
| Documentation | Search docs, check links, summarize stale pages, generate indexes, and compare docs against source code. |
| Design system | Pull design-tool context, inspect component libraries, export screenshots, and compare UI implementation against design references. |
| Web research | Use search/crawl tools to refresh current API, library, pricing, or standards references. |
| Browser verification | Use browser automation tools to capture screenshots, inspect accessibility, and verify visual states. |
| Repository workflow | Read issues, pull requests, checks, review comments, and CI logs through repository connectors. |
| External docs | Sync external documents, tables, or slide decks into local reference indexes. |
| Memory | Generate memory indexes, detect stale memory, and route relevant memory snippets without loading everything. |
| Security | Scan docs for secret-like strings before publishing or packaging bundles. |

## Adapter Rule

Do not make MCP-specific files the portable source of truth. Treat them as local adapters.

Good pattern:

```text
portable framework rule/protocol -> local MCP adapter -> generated report/index
```

Avoid:

```text
MCP-only hidden config -> undocumented behavior -> no framework-visible fallback
```

## Capability Matrix

When adopting MCPs, document capabilities like this:

| Capability | Preferred MCP/tool | Fallback | Secrets required | Validation |
|---|---|---|---|---|
| Search current docs | `<tool>` | browser/manual source lookup | no/yes | source links recorded |
| Inspect repo issues | `<tool>` | local notes/manual repository UI | yes | issue/PR links resolve |
| Capture UI screenshot | `<tool>` | local browser command/manual screenshot | no | screenshot saved |

## Safety Rules

- Record API keys by environment variable name only.
- Keep secret values out of docs, memory, and generated indexes.
- Use MCPs to improve observability, not to hide workflow steps or replace the framework.
- Keep a script or manual fallback for important validation.
- Prefer primary sources when MCPs retrieve current or high-stakes information.
- Note which MCP-generated outputs are derived caches, not canonical source material.
