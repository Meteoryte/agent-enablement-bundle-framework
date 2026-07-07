# Folder Structure Protocol

Folder structure is a routing interface for humans and agents. It should reveal ownership, currentness, and allowed work before any file is edited.

## Core Rule

Separate durable guidance, active work, references, archives, generated output, and secrets-adjacent runtime files.

Recommended high-level areas:

```text
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
workflows/
memory/
scripts/
```

Small repos can collapse this structure. Keep the distinctions even when the folders are simpler.

## Local Folder Contract

Every major folder should answer:

| Question | Where to answer |
|---|---|
| What belongs here? | `README.md` |
| What is current or deprecated? | `README.md`, `STATUS.md`, or command center |
| What rules apply locally? | local agent instructions or folder README |
| What validates this folder? | checklist, script, test command, or manual check |
| What is generated and disposable? | `README.md`, `.gitignore`, or output folder note |

## Currentness Labels

Use explicit labels in folder READMEs and indexes:

```text
current
active
reference-only
generated
archived
deprecated
superseded
backup
experimental
```

Do not let old work look canonical merely because it is nearby.

## Generated Output Rule

Generated artifacts should live in clearly named output folders and should not become canonical unless a human or workflow promotes them.

Good:

```text
workflows/research-topic/01-source-scan/output/
```

Avoid:

```text
docs/final-output-from-agent.md
```

## Reference Library Rule

Reference folders may preserve third-party names, original casing, and copied examples. Add an index that states:

- source
- license or usage constraints when known
- why it is included
- whether it is canonical, inspiration, or raw evidence
- any validation needed before using it

## Archive And Backup Rule

Archive and backup folders are non-current by default. Agents should not edit or restore them unless the task explicitly asks for archive work.

## Checklist

- [ ] Active work, durable standards, references, archives, and generated output are separated.
- [ ] Major folders have README or local contract docs.
- [ ] Currentness labels are visible.
- [ ] Reference-only material cannot be mistaken for canonical source.
- [ ] Generated output has an output folder and promotion rule.
- [ ] Archive and backup folders are marked non-current.
