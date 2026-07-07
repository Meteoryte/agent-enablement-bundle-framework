# Memory Integrations Template

Use this file to document how each agent surface reads the same markdown memory store.

| Agent surface | Read mechanism | Write allowed? | Notes |
|---|---|---|---|
| `<surface>` | Points to `memory/MEMORY.md` | yes/no | `<notes>` |

Rules:

- Every surface reads the same canonical memory index.
- Only approved surfaces write memory.
- Generated indexes are derived from markdown.
- No tool gets its own hand-edited memory fork.
