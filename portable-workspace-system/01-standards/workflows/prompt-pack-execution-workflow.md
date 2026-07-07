# Prompt Pack Execution Workflow

Use this workflow when work arrives as a staged prompt pack, multi-file instruction set, or large implementation brief.

## Core Rule

Digest the full pack before editing, then execute phases in dependency order.

Do not skip ahead to later phases when earlier phases or prerequisite packs are incomplete.

## Workflow

1. Read the pack index, root operator prompt, phase prompts, guardrails, references, templates, and acceptance checklist.
2. Compare the pack against the live repo state.
3. Identify completed, partial, missing, blocked, and superseded work.
4. Finish prerequisite phases first.
5. Execute the next phase in the intended order.
6. Validate after each meaningful slice.
7. Promote reusable rules into the standards library.
8. State deferred work explicitly.

## Prompt Pack Contents

A good pack includes:

- context and objective
- non-goals and boundaries
- implementation phases
- source-of-truth references
- file/folder ownership
- schemas or contracts
- acceptance checklist
- validation commands or manual checks
- migration or rollback notes

## Visual Pack Addendum

When a pack includes screenshots, generated art, prototypes, game UI, canvas, HUDs, or HTML mockups:

- separate visual intent from implementation assets
- do not bake live data into images
- keep live text and accessibility in the UI layer
- define asset tickets before generating art
- use prototype HTML as visual reference, not production structure
- verify the rendered app, not only the mockup

## Completion Standard

Do not claim a pack is complete when only docs were created. Execution means the requested runtime behavior, wiring, docs updates, and validation evidence exist.

## Checklist

- [ ] Full pack read before edits.
- [ ] Live repo state reconciled.
- [ ] Prerequisites completed first.
- [ ] Phases executed in order.
- [ ] Validation run after meaningful slices.
- [ ] Reusable rules promoted.
- [ ] Deferred work named clearly.
