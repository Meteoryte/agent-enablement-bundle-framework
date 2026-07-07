# 01 Stage Context Template

## Purpose

State what this stage accomplishes.

## Inputs

| Source | File/Location | Section/Scope | Why |
|---|---|---|---|
| User request | conversation or intake file | relevant request | Defines task scope. |

## Process

1. Read required inputs.
2. Identify missing or conflicting information.
3. Produce the stage output.
4. Run quality checks.

## Outputs

| Artifact | Location | Format |
|---|---|---|
| Stage output | `output/stage-output.md` | Markdown |

## Quality Checks

- Output uses only allowed inputs.
- Assumptions are explicit.
- Missing information is labeled.
- The output is ready for the next stage or for human review.

## Stop Conditions

Stop if required inputs are missing, contradictory, or outside this workflow's scope.
