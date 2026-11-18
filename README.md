# Inventory Replenishment and Reporting Optimization

A fictional business analysis case study, built as a portfolio piece.

**Status: demo / sample.** The company, numbers and stakeholders are invented. It is not based on a real organization, client, project or dataset, and no real company data was used.

## What this is

A retail distributor has late replenishment, stockouts on fast sellers, excess stock on slow sellers, and slow manual weekly reports. I wrote the business analysis documents for a proposed fix using Power BI, Power Automate and Microsoft Copilot as optional analysis support.

I wrote this to practise business analysis work: process analysis, requirements, user stories, traceability and testing, and to show how I check AI-generated drafts instead of accepting them.

## Documents (read in this order)

| File | What it covers |
|---|---|
| `docs/part-1-assessment.pdf` | Assumptions, objectives, scope, stakeholders, RACI, current-state and future-state process, forecasting and reorder-point approach |
| `docs/part-2-requirements.pdf` | Business, functional, non-functional, data and reporting requirements. User stories (MoSCoW), test cases, traceability, success measures, approval diagrams |
| `docs/part-2-addendum.pdf` | Gap remediation after review: completed stories, test cases, requirement mapping, corrected measures, known gaps |
| `ai-vs-me.md` | What the AI produced, what I found wrong, and what I changed |

Diagrams are in `diagrams/` (also embedded in the PDFs). The AI-drawn diagram I rejected during review is in `screenshots/chart-c-before-review.png`.

## How it was made

- **Tool:** Microsoft Copilot (the Copilot app, not Microsoft 365 Copilot inside Word).
- **Method:** I gave Copilot a fictional scenario and asked for the documents in stages. I reviewed each output, listed the problems, and asked for corrections. This took three rounds.
- **Review support:** I also used Claude (Anthropic's assistant) to help review the drafts and spot problems, and I made the final edits myself.
- Details of each round are in `ai-vs-me.md`.

## What I checked in the AI output

- Whether forecasting was actually defined, not just mentioned.
- Whether priorities were consistent (reorder points cannot be a Must if the forecast they depend on is a Should).
- Whether every pain point traces to a requirement, a story and a test case, and the reverse.
- Whether the approval diagram kept the control it claimed: escalation replaces a delayed approver and never removes a required approval.
- Whether claims such as "fully covered" were true. They were not, so I replaced them with a list of known gaps.

## What this does NOT show

- It is not real client work and not a finished enterprise Business Requirements Document.
- I have not worked with ERP systems such as SAP or IFS.
- It does not show live stakeholder workshops, discovery calls or running user acceptance testing.
- Microsoft product capabilities and licensing are **not verified** against Microsoft documentation. Items marked "to be confirmed" need checking before any real use.
- All numbers are assumptions or placeholders.

## Known gaps

The addendum lists them. In short: several requirements have no linked test case, some non-functional requirements are not yet measurable, and one test case (TC7) has no script.

## Author

Denny Jose, Kingston, Ontario. Post-Graduate Certificate in Business Analytics, St. Lawrence College.
