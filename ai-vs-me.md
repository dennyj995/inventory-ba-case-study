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

## Round 4: Part 3 (change impact, operational readiness, change control)

I wrote Part 3 in three stages and reviewed each one.

**3A: change impact and training**
- The first draft left out the Business Analysts who build the weekly reports. They are changed the most by automated reporting. Report pain points had been assigned only to the people who read reports. I added the group and linked P2, P4, P5, P11, P16 and P17 to it.
- The spreadsheet pain points had no owner. I linked them to Inventory Planners and Business Analysts.
- A claim that Buyers would spend less effort preparing recommendations contradicted Part 2, where purchase order entry stays manual. I removed it.
- Group names and training owners did not match (for example "Project Sponsor", "New Starters"). I made them consistent with the stakeholder table and the RACI.

**3B: operational readiness**
- An assumption said User Acceptance Testing "has been completed" while the checklist item for it was not started. I changed it to "will be completed".
- Training for Warehouse Managers and IT was missing from the checklist even though 3A required it before go-live.
- The fallback plans did not keep the two-approval rule for above-threshold orders. I added it, and added that manual approvals must record who, what, when and why.
- The first fallback used old data without recording its age. I added a record of the age and a hold on above-threshold orders while data is stale.
- The traceability section claimed there were no unlinked items, but several open questions had no link. After the correction I counted the links and wrote the real list of pain points that Part 3B does not link.

**3C: change control**
- The flow sent a rejected request back to the start and closed a deferred request. A rejected request now goes back to the requester, and a deferred request goes to a list for later review.
- The worked example for an approval threshold change did not mention the two-approval rule, audit logging or notifications. I added them.
- The second worked example linked a trend-reporting requirement to an exception report. I replaced it with the correct requirement, a data requirement and the readiness items for the definitions it depends on. I also made it a deferred request so the log shows more than one outcome.
- The approval matrix had no row for a new or changed report. I added one so the approver in the example is supported by the matrix.

## What I did by hand

- Document control (version, date, prepared by, related documents).
- Removed the AI's self-assessment sections and the "fully covered" claims.
- Resized and placed the diagrams, and fixed captions.
- Kept all numbers as labelled assumptions.
- Merged Part 3A, 3B and 3C into one document and checked the owners, IDs and links across them.

## What I did not verify

- Microsoft Copilot, Power BI and Power Automate capabilities and licensing.
- Whether Power BI can forecast demand at product level.
- Anything about real inventory systems or real companies.
