# Reference Library Curation Workflow

Use this workflow when adding external libraries, docs, examples, UI kits, prompt packs, or copied references.

## Core Rule

Make references observable. A future agent should know where the reference came from, why it exists, how current it is, and whether it is canonical or inspiration only.

## Workflow

1. Identify the need the reference solves.
2. Prefer primary sources for technical behavior.
3. Check license, cost, API-key requirements, and freshness.
4. Copy or link only what is useful and allowed.
5. Add an index entry with source, purpose, status, and validation notes.
6. Mark whether the reference is canonical, source mirror, inspiration, or archive.
7. For libraries, record install command, import path, docs link, and local usage owner.
8. For UI references, record visual role, implementation boundaries, and verification loop.

## Reference Index Shape

```text
Name:
Source:
License or terms:
Cost:
Keys required:
Purpose:
Canonical status:
Local owner:
Validation:
Last checked:
```

## Status Labels

```text
canonical
source-mirror
reference-only
inspiration
candidate
deprecated
blocked
superseded
```

## Checklist

- [ ] Need is clear.
- [ ] Source and license/terms are recorded.
- [ ] Cost and key requirements are recorded.
- [ ] Canonical status is labeled.
- [ ] Local owner and validation path are known.
- [ ] Reference index was updated.
