# AI vs me: what Copilot produced and what I changed

Tool: Microsoft Copilot app. I also used Claude (Anthropic) to help me review drafts. The decisions and final edits are mine.

## Round 1: first draft (Part 1)

**What Copilot produced:** assumptions, executive summary, stakeholder table, current-state steps, future-state steps.

**Problems I found**
- Forecasting was mentioned but never defined.
- Power Automate was said to refresh data, which I flagged to verify (Power BI has its own scheduled refresh).
- No traceability: nothing linked problems to requirements or tests.
- Pain points were generic and repeated.
- No actors or controls on the process steps, no scope or objectives, no RACI.
- "Near real-time" contradicted the admitted unknown ERP refresh rate.
- Copilot added a line praising its own document. I removed it.

## Round 2: revision

**What improved:** IDs for pain points, bottlenecks and risks (P, B, R), actors and controls, scope and out-of-scope, RACI, a forecasting approach, reorder point formula.

**Problems I found**
- The diagram sent a rejected approval back to the Copilot step instead of the planner, and had a duplicate path from monitoring to forecasting.
- Forecast generation was a Should while reorder points were a Must, although reorder points depend on the forecast. I changed forecast generation to a Must.
- Test cases were titles only. Acceptance criteria were vague ("reorder points are calculated").
- A Won't Have category was missing.
- Success measures had no formulas.

## Round 3: remediation (addendum)

**What improved:** full stories in Given/When/Then, detailed test cases, requirement mapping, formulas (for example forecast accuracy as 100 minus MAPE), Won't Have stories, redrawn diagrams.

**Problems I found**
- The overdue diagram (see `screenshots/chart-c-before-review.png`) let the Operations Manager's late approval skip the second required approval. I asked for it to be redrawn so escalation replaces a delayed approver for the same step only. The corrected version is `diagrams/chart-c2-overdue.png`.
- KPI Dashboards appeared after forecast generation, although dashboards do not depend on the forecast. I removed that branch.
- The coverage table claimed "Fully Covered", but several requirements have no linked test case and TC7 has no script. I replaced the claim with a Known Gaps list.
- Document control said "Senior Business Analyst", "Reviewed By" and "Approved By", and used placeholders as dates and versions. No one reviewed or approved this document, and I am not a Senior Business Analyst. I corrected all of it.

## What I did by hand

- Document control (version, date, prepared by, related documents).
- Removed the AI's self-assessment sections and the "fully covered" claims.
- Resized and placed the diagrams, and fixed captions.
- Kept all numbers as labelled assumptions.

## What I did not verify

- Microsoft Copilot, Power BI and Power Automate capabilities and licensing.
- Whether Power BI can forecast demand at product level.
- Anything about real inventory systems or real companies.
