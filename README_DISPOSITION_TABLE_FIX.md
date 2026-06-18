# README Disposition Table Fix

Use this section to replace any README disposition table whose thresholds do not match the workbook logic.

## Disposition and routing

| Disposition | Condition | Route |
| --- | --- | --- |
| **Manual** | `EIRA <= 2` | Hold and route to EIRA. The gap is institutional, and closing it is the work of readiness, not workflow triage. |
| **Manual** | `Impact <= 2` and `EIRA > 2` | Hold manual or deprioritize. The workflow does not earn AI involvement at present. |
| **Hybrid** | `Impact >= 3`, `EIRA >= 3`, and `Consequence >= 4` | Route to a Minimum Decision Contract, then ATM™ outcome instrumentation. |
| **Automated** | `Impact >= 3`, `EIRA >= 3`, and `Consequence <= 3` | Route to ATM™ outcome instrumentation. |

When a Manual disposition is driven by both low impact and a readiness gap, the readiness gap takes precedence. The workflow routes to EIRA because the institutional gap is the more consequential finding.
