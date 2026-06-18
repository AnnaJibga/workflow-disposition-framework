# GitHub Record: Ship WDF v1.0 for Client Engagement Readiness

## Title

Ship Workflow Disposition Framework v1.0 and engagement wrapper

## Repository

Intended repository: `AnnaJibga/workflow-disposition-framework`

Current status: repository path should be created or confirmed before publishing. The `CITATION.cff` file is prepared for this repository path.

## Purpose

Prepare the Workflow Disposition Framework (WDF™) as a GitHub-ready proof artifact and client-engagement entry point.

This release makes the WDF logic inspectable at the public repository level while keeping the commercial application, facilitation, workbook interpretation, and advisory packaging inside Foundeon engagement delivery.

## Track 1 - WDF ship-readiness

### Files to publish at repository root

- `README.md`
- `SCORING_METHODOLOGY.md`
- `LICENSE.md`
- `CITATION.cff`

### Supporting file

- `docs/README_DISPOSITION_TABLE_FIX.md`

### Acceptance criteria

- README disposition thresholds match the workbook logic.
- `SCORING_METHODOLOGY.md` documents the actual order of operations.
- Manual gate is binary at `Impact <= 2 OR EIRA <= 2`.
- Hybrid trigger is `Consequence >= 4` after impact and readiness clear the gate.
- Automated remains the residual disposition, not the target.
- Lowest relevant EIRA dimension is used rather than an average.
- Routing rule is explicit and terminates in an owned next step.
- License states CC BY-NC-ND 4.0 and commercial-use restrictions.
- Trademark note is included without over-explaining status.
- `CITATION.cff` renders GitHub's citation function.

## Track 2 - Engagement wrapper

### File to publish or store with client-ready assets

- `client-engagement/Foundeon_Workflow_Disposition_Engagement.docx`

### Engagement positioning

The engagement turns "run EIRA, then WDF" into a sellable Foundeon engagement.

The client outcome is a complete disposition of AI-candidate workflows, each read against readiness and assigned a disposition: Manual, Hybrid, or Automated. Each disposition routes to an owned next step rather than remaining a label.

### Engagement sequence

1. Establish readiness through EIRA.
2. Inventory AI-candidate workflows.
3. Score each workflow for impact and consequence against readiness.
4. Assign disposition and route.
5. Sequence the build order.
6. Deliver the executive readout.

## Confirmations before going live

- `date-released` is currently set to `2026-06-17`. Change it if the public release date should be different.
- `repository-code` is currently set to `https://github.com/AnnaJibga/workflow-disposition-framework`. Confirm after the repository is created.
- The README table has been corrected in full in `README.md`, with the paste-in version also available in `docs/README_DISPOSITION_TABLE_FIX.md`.

## Suggested commit plan

Commit 1: Add WDF scoring methodology, license, citation, and README

Commit 2: Add README disposition table fix note and release notes

Commit 3: Add Foundeon Workflow Disposition Engagement wrapper

## Suggested release tag

`v1.0.0`

## Suggested release title

Workflow Disposition Framework v1.0

## Suggested release notes

This release publishes the Workflow Disposition Framework v1.0 repository structure, scoring methodology, license, citation metadata, README threshold alignment, and Foundeon engagement wrapper for client-readiness use.

## Final ship checklist

- [ ] Create or confirm repository: `AnnaJibga/workflow-disposition-framework`
- [ ] Upload root files
- [ ] Upload `docs/README_DISPOSITION_TABLE_FIX.md`
- [ ] Upload `client-engagement/Foundeon_Workflow_Disposition_Engagement.docx`
- [ ] Confirm README renders cleanly
- [ ] Confirm GitHub citation button appears
- [ ] Confirm license displays correctly
- [ ] Create release tag `v1.0.0`
- [ ] Add repository description: `Workflow disposition logic for sequencing AI-candidate workflows against enterprise readiness.`
- [ ] Add repository topics: `ai-governance`, `workflow-disposition`, `enterprise-ai`, `ai-readiness`, `foundational-data-products`
