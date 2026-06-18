# Release Notes

## Workflow Disposition Framework v1.0

Release date: 2026-06-17

This release prepares the Workflow Disposition Framework (WDF™) for GitHub publication and Foundeon client-engagement readiness.

## Included

- Public README for the WDF repository.
- Scoring methodology documenting the workbook logic.
- CC BY-NC-ND 4.0 license file with commercial-use and trademark notes.
- `CITATION.cff` metadata for GitHub citation rendering.
- README disposition table correction.
- Foundeon Workflow Disposition Engagement wrapper.
- Internal GitHub record and ship checklist.

## Core logic

```text
IF Impact <= 2 OR EIRA <= 2:
    Disposition = Manual
ELSE IF Consequence >= 4:
    Disposition = Hybrid
ELSE:
    Disposition = Automated
```

## Routing

- Manual due to readiness gap routes to EIRA.
- Manual due to low impact is held manual or deprioritized.
- Hybrid routes to a Minimum Decision Contract, then ATM™ outcome instrumentation.
- Automated routes to ATM™ outcome instrumentation.

## Notes before publication

- Confirm the public release date.
- Confirm the final repository path.
- Confirm whether the engagement wrapper should live in this public repo, a private repo, or Foundeon's client-asset library.
