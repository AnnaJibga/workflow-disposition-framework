# WDF™ Scoring Methodology

*Workflow Disposition Framework, v1.0. Part of the [Foundational Data Products™](https://foundationaldataproducts.com) methodology and the DSIL™ framework, by [Anna Jibgashvili](https://www.linkedin.com/in/annajibgashvili/).*

---

This document specifies the disposition logic in the WDF Disposition Map. The README states what the framework does and where it sits. This document states how the disposition is computed, so the logic can be inspected, challenged, and trusted by the leaders who act on its output.

## The three inputs

Each workflow is scored on three whole-number inputs from 1 to 5. The workbook enforces this range on the input cells.

**Impact (1–5).** How much the business moves if the workflow runs faster, better, or cheaper, measured against revenue, margin, retention, or speed to decision. Impact answers: is this workflow worth involving AI in at all.

**Consequence (1–5).** The cost if the AI produces a wrong output: erroneous data, degraded customer experience, regulatory exposure, reputational weight. Consequence answers: what happens when, not if, the AI is wrong.

**Lowest relevant EIRA dimension (1–5).** The institution's readiness to own this class of workflow, taken as the lowest of the relevant [Enterprise Identity Readiness Assessment](https://github.com/AnnaJibga/enterprise-identity-readiness-assessment) dimension scores. The lowest dimension is used rather than an average, because readiness is gated by its weakest relevant element, not lifted by its strongest. A workflow is only as governable as the dimension the institution is least ready to own.

## The disposition rule

The disposition is computed in this order. The order matters: the readiness and impact gates are evaluated before the consequence test, because a workflow the institution cannot own, or that does not matter, is not a candidate for automation regardless of how its consequence reads.

```
IF Impact <= 2 OR EIRA <= 2:
    Disposition = Manual
ELSE IF Consequence >= 4:
    Disposition = Hybrid
ELSE:
    Disposition = Automated
```

### Why these thresholds

**The Manual gate is binary at 2, not graduated.** A score of 1 or 2 on either Impact or readiness sends the workflow to Manual before any other test runs. This is deliberate. The gate is not a measure of degree; it is a floor. Below it, the question is not how to dispose the workflow but whether the precondition for disposing it at all has been met. A low-impact workflow does not earn the cost of governance. A workflow the institution scores 1 or 2 on its lowest relevant readiness dimension is not one the institution is positioned to own, and ownership is the precondition for responsible automation. Holding the gate binary keeps the framework from rationalizing automation of a workflow that fails a precondition simply because its other scores are high.

**The Hybrid trigger is Consequence >= 4.** Once a workflow clears the impact and readiness gates, high consequence is the deciding factor. A workflow that is worth automating, and that the institution is ready to own, but whose wrong output carries serious cost, is dispositioned Hybrid: AI drafts, a human holds the decision. The threshold is set at 4 rather than 3 so that Hybrid is reserved for genuinely high-consequence work, not assigned by default. A consequence of 3 is treated as tolerable under instrumentation rather than requiring a human decision-holder.

**Automated is the residual, not the goal.** A workflow is dispositioned Automated only when it has cleared the impact gate, cleared the readiness gate, and carries a consequence the institution can absorb under outcome instrumentation. Automated is what remains after the gates and the Hybrid test, not a target to optimize toward. The framework's stated position is that the highest-value disposition is most often Hybrid, not full automation.

## The routing rule

The disposition terminates in a routing decision, not a tag. A tag is a recommendation; a route is an owned next step.

| Disposition | Routes to |
| ----------- | --------- |
| **Manual**, readiness gap (EIRA <= 2) | Hold and route to EIRA. The gap is institutional, and closing it is the work of readiness, not workflow triage. |
| **Manual**, low impact (Impact <= 2, EIRA > 2) | Hold manual or deprioritize. The workflow does not earn AI involvement at present. |
| **Hybrid** | Minimum Decision Contract, then ATM™. The contract makes the hybrid arrangement operable before the workflow ships; ATM™ instruments it afterward. |
| **Automated** | ATM™ outcome instrumentation. A shipped workflow is measured for whether it holds up, not assumed to. |

When a Manual disposition is driven by both a low impact score and a readiness gap, the readiness gap takes precedence in routing: the workflow routes to EIRA, because the institutional gap is the more consequential finding.

## What the score does not do

The score does not rank a workflow against industry peers. It does not select a vendor or model. It does not assess readiness; it reads against an EIRA result produced separately. And it does not settle a disposition permanently. Workflows and readiness shift, and re-running the disposition is the reassessment mode, where much of the framework's value sits.

## Scoring discipline

The output is only as honest as the input. Self-flattering scores, inflated readiness in particular, produce a disposition map that authorizes automation the institution cannot actually support. The readiness input should come from a completed EIRA, not from estimation at the point of scoring. Where EIRA has not been run, the consequence read is performed in isolation and the output should be treated as provisional.

---

*© 2026 Anna Jibgashvili | Foundational Data Products™ | DSIL™ | CC BY-NC-ND 4.0*
