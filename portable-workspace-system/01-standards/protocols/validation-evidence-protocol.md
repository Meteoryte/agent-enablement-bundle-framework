# Validation Evidence Protocol

Every important rule should have a way to prove it was followed.

## Core Rule

Do not call work complete until the relevant validation interface has run or the skip is explicitly explained.

Validation can be automated or manual, but it must be named.

## Validation Interfaces

| Interface | Use for |
|---|---|
| Unit or integration tests | Behavior, boundaries, regressions |
| Type check or compile | Static correctness |
| Lint or formatting | Code quality and style constraints |
| Naming audit | File, symbol, and document naming rules |
| Link check | Documentation integrity |
| Schema validation | Registries, tool contracts, JSON/YAML |
| Fixture regression | Scoring, prompts, parsers, classifiers |
| Historical replay | Drift and behavioral impact analysis |
| Browser screenshot loop | UI layout, state, accessibility, overflow |
| Manual inspection | Cases where automation is unavailable |
| Secret scan | Public export safety |

## Evidence Shape

In final notes, record:

```text
Changed:
Validation run:
Validation skipped:
Known risk:
Next action:
```

For high-risk work, include the command or exact manual check.

## Fixture And Replay Pattern

Use fixtures when a rule has known examples. Use replay when saved real-world inputs exist and drift matters.

Healthy fixture:

- one behavior claim
- descriptive filename
- stable inputs
- narrow expected output

Healthy replay:

- baseline before change when possible
- replay after change
- drift explained
- large outliers reviewed

## UI Verification Pattern

For visible UI changes:

1. Identify the visual reference.
2. Run the real surface.
3. Capture or inspect the relevant sizes and states.
4. Check spacing, overflow, focus, loading, empty, error, contrast, wrapping, clipping, and layout shift.
5. Patch and repeat if the surface fails inspection.
6. Report what was verified.

## Skip Policy

Skipped validation is acceptable only when explained:

```text
Skipped screenshot capture because the app requires unavailable credentials; performed static component inspection and type check instead.
```

Do not say validation passed when it did not run.

## Checklist

- [ ] Is every important rule tied to a validation interface?
- [ ] Did the relevant check run?
- [ ] Are skipped checks named with a reason?
- [ ] Are fixture changes paired with behavior changes?
- [ ] Is high-risk work backed by stronger evidence?
