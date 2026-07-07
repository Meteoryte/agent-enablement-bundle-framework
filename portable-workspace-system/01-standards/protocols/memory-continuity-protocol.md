# Memory Continuity Protocol

Use this protocol when a workspace needs durable cross-session context for agents.

## Core Rule

Memory should be useful, minimal, markdown-first, and safe. It should not become a secret store, chat dump, or replacement for source-of-truth docs.

## Memory Belongs To

Memory can record:

- durable preferences
- known project conventions
- recurring user goals
- current long-running initiatives
- links to canonical docs
- integration notes
- unresolved questions
- last verified dates

Memory should not record:

- API keys or tokens
- sensitive user data
- raw private chat transcripts unless explicitly approved
- generated guesses
- facts that belong in architecture, workflow, or source docs
- anything that would be unsafe to share with the selected model provider

## Memory Shape

Use plain files:

```text
memory/
  README.md
  MEMORY.md
  INTEGRATIONS.md
```

`MEMORY.md` is durable human-readable context. `INTEGRATIONS.md` explains which agent surfaces or tools read the memory and how.

## Update Workflow

1. Decide whether the fact belongs in memory or in canonical project docs.
2. Add the shortest durable statement that will help future work.
3. Link to source-of-truth docs instead of copying them.
4. Add a last-verified date when freshness matters.
5. Remove stale or superseded memory during review loops.

## Agent Use

Agents should read only relevant memory. Do not load all memory by default when the task is narrow.

## Checklist

- [ ] The item belongs in memory, not canonical docs.
- [ ] No secrets or private runtime dumps are included.
- [ ] Source-of-truth docs are linked.
- [ ] Freshness-sensitive entries include dates.
- [ ] Stale memory is pruned during review.
