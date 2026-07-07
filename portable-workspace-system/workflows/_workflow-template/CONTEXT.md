# Workflow Context Template

## Purpose

State the repeatable outcome this workflow produces.

## Stages

| Stage | Job |
|---|---|
| 01-stage | Replace with the first bounded step. |

## Global Workflow Rules

- Read only the inputs named by the current stage.
- Save outputs to the current stage's `output/` folder.
- Human-edited outputs become the source of truth for later stages.
- Later stages may read earlier outputs; earlier stages should not read later outputs.
- Stop when inputs are missing, contradictory, or outside scope.

## Completion

The workflow is complete when all required stage outputs pass their quality checks and any human review checkpoints are resolved.
