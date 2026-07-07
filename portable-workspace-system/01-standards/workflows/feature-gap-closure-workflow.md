# Feature Gap Closure Workflow

Use this workflow to track and close features that are planned, partial, deferred, or misrepresented as complete.

## Core Rule

A feature gap document should say what exists, what is missing, why it matters, and the next concrete action.

## Gap Record Shape

```text
Title:
Status:
Priority:
What exists:
What is missing:
Evidence:
Next action:
Validation:
Owner or owning area:
Updated:
```

Use stable statuses:

```text
not implemented
in progress
partial
deferred
blocked
reference-only
complete
superseded
```

## Priority Tiers

Sort gaps by user value and risk:

| Tier | Meaning |
|---|---|
| Tier 1 | Core daily workflow or critical safety gap |
| Tier 2 | Spec-ready build with no or partial code |
| Tier 3 | Partially built convenience or polish |
| Tier 4 | Backlog, research, or nice-to-have |

## Closure Workflow

1. Pick the highest-priority open item.
2. Read the evidence and owning source files.
3. Confirm the current live state before editing.
4. Implement only the next concrete action unless the user asks for a broader slice.
5. Run the named validation interface.
6. Update the gap record with new status and evidence.
7. Move closed items into a dated closed log.

## Avoid

- Do not mark complete because a design doc exists.
- Do not treat a reference prototype as shipped behavior.
- Do not close a gap without validation or a named reason validation was skipped.
- Do not let old backlog docs override fresher source evidence.

## Checklist

- [ ] Is the feature state grounded in current source evidence?
- [ ] Is the next action concrete?
- [ ] Is the status honest?
- [ ] Did validation run?
- [ ] Was the gap doc updated after work?
