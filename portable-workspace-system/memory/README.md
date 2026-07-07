# Memory

Purpose: optional cross-session context for AI-assisted work.

Use memory only when durable context is not already captured in code, docs, issues, plans, or decisions.

Rules:

- Markdown stays canonical.
- Generated indexes are disposable.
- One memory fact per file.
- No secrets, tokens, private credentials, or sensitive raw data.
- Agent-specific loaders point here; they do not own separate memory stores.
