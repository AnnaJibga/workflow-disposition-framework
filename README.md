# Workflow Disposition Framework (WDF™)

**Workflow Disposition Framework (WDF™)** is a Foundeon framework for sequencing AI-candidate workflows against institutional readiness.

WDF helps leaders decide whether a workflow should remain **Manual**, move through a **Hybrid** human-AI operating pattern, or proceed toward **Automated** execution with outcome instrumentation.

The framework is designed to follow the **Enterprise Identity Readiness Assessment (EIRA)**. EIRA establishes the readiness baseline. WDF then reads each AI-candidate workflow against that baseline and routes the workflow to an owned next step.

## Why this exists

AI workflow selection should not be driven only by technical feasibility or productivity potential. A workflow may be technically automatable and still be inappropriate to automate if the institution is not ready to own the business meaning, decision context, governance, accountability, and evidence requirements the workflow depends on.

WDF makes the disposition decision explicit.

It asks:

- Is the workflow worth involving AI in at all?
- What is the consequence if the AI-supported output is wrong?
- Is the institution ready to own this class of workflow?
- What next step should this workflow route to?

## Repository contents

| File                                   | Purpose                                                                   |
| -------------------------------------- | ------------------------------------------------------------------------- |
| `README.md`                            | Public orientation to the framework and repository.                       |
| `SCORING_METHODOLOGY.md`               | Defensible scoring logic, thresholds, and routing rules.                  |
| `LICENSE.md`                           | CC BY-NC-ND 4.0 license summary, commercial-use note, and trademark note. |
| `CITATION.cff`                         | Citation metadata for GitHub's **Cite this repository** function.         |
| `docs/README_DISPOSITION_TABLE_FIX.md` | Paste-in replacement table for README threshold alignment.                |
| `GITHUB_RECORD.md`                     | Internal GitHub issue or release record for shipping v1.0.                |
| `RELEASE_NOTES.md`                     | Release notes for v1.0.                                                   |

## Client Engagement Use

WDF™ can be applied as part of a Foundeon advisory engagement that begins with EIRA readiness assessment, inventories AI-candidate workflows, applies the WDF™ disposition logic, and produces a sequenced build order with owned next steps.

A separate Foundeon Workflow Disposition Engagement wrapper exists for client delivery and commercial scoping. That document is not published in this repository.


## Inputs

Each workflow is read through three whole-number inputs from 1 to 5.

| Input | Meaning |
| --- | --- |
| **Impact** | How much the business moves if the workflow runs faster, better, or cheaper. |
| **Consequence** | The cost if the AI-supported output is wrong. |
| **Lowest relevant EIRA dimension** | The institution's readiness to own this class of workflow, taken from the lowest relevant EIRA dimension rather than an average. |

The lowest relevant EIRA dimension is used because readiness is gated by the weakest relevant element. A workflow is only as governable as the dimension the institution is least ready to own.

## Disposition rule

```text
IF Impact <= 2 OR EIRA <= 2:
    Disposition = Manual
ELSE IF Consequence >= 4:
    Disposition = Hybrid
ELSE:
    Disposition = Automated
```

The order matters. Impact and readiness gates are evaluated before consequence because a workflow the institution cannot own, or that does not matter enough, is not a candidate for automation regardless of consequence.

## Disposition and routing

| Disposition | Condition | Route |
| --- | --- | --- |
| **Manual** | `EIRA <= 2` | Hold and route to EIRA. The gap is institutional, and closing it is the work of readiness, not workflow triage. |
| **Manual** | `Impact <= 2` and `EIRA > 2` | Hold manual or deprioritize. The workflow does not earn AI involvement at present. |
| **Hybrid** | `Impact >= 3`, `EIRA >= 3`, and `Consequence >= 4` | Route to a Minimum Decision Contract, then ATM™ outcome instrumentation. |
| **Automated** | `Impact >= 3`, `EIRA >= 3`, and `Consequence <= 3` | Route to ATM™ outcome instrumentation. |

When a Manual disposition is driven by both low impact and a readiness gap, the readiness gap takes precedence. The workflow routes to EIRA because the institutional gap is the more consequential finding.

## Intended use

WDF is designed for enterprise leaders sequencing AI workflow portfolios, especially in regulated or high-accountability environments.

It supports two use cases:

1. **Greenfield sequencing** - deciding which AI-candidate workflows should ship first, ship later, stay hybrid, or remain manual.
2. **Live estate reassessment** - reviewing deployed AI workflows to identify where disposition has drifted and needs to be re-routed.

## Engagement wrapper

The Foundeon Workflow Disposition Engagement packages the sequence as:

1. Run EIRA.
2. Inventory AI-candidate workflows.
3. Score impact and consequence against the readiness result.
4. Assign Manual, Hybrid, or Automated disposition.
5. Route each workflow to an owned next step.
6. Convert the disposition map into a sequenced build order.

The engagement wrapper is included in `client-engagement/Foundeon_Workflow_Disposition_Engagement.docx`.

## License

This work is licensed under **CC BY-NC-ND 4.0**.

You may share it with attribution. You may not use it commercially or distribute modified versions without permission.

For commercial licensing or advisory engagement, contact Foundeon.

## Citation

Use the repository citation generated from `CITATION.cff`.

## Trademark note

WDF™, DSIL™, and Foundational Data Products™ are marks of Anna Jibgashvili / Foundational Data Products™. The license applies to copyrightable content and does not grant rights to use these marks.
