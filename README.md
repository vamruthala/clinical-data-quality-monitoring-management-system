# Clinical Data Quality Monitoring & Management System

A clinical data-management case study showing how study teams can monitor data quality from collection through Data Coordinating Center (DCC) submission.

## Business question

How can teams detect incomplete records, QC failures, and submission blockers across sites and data streams?

## Role and approach

Designed the workflow across MS Access and Excel, then built a Tableau dashboard for completeness, QC, issue triage, and submission progress.

`Clinical assessments / EEG / wearable / biospecimen`
→ participant and metadata tracking
→ validation checks
→ issue triage and SLA tracking
→ Tableau monitoring
→ DCC readiness review

## Scope and reported measures

- 300 participants across 4 research sites; 4 data streams.
- 5,324 validation checks; 891 issues tracked through triage.
- 94% reported overall completeness; 91% reported submission readiness.

| Measure / formula | How to interpret it |
|---|---|
| Completeness: `AVG([Completeness_Pct]) / 100` | Converts the average source score to a 0–1 fraction; 0.94 corresponds to 94%. |
| Form completion: `IF [Form_Complete] = "Yes" THEN 1 ELSE 0 END` | Converts each form to a binary flag for completion-rate aggregation. |
| QC pass: `IF [Status Pass] = "Pass" THEN 1 ELSE 0 END` | Flags records passing QC for dashboard monitoring. |
| Submission readiness | Reported as 91%; the source summary does not define its calculation rule. |

## Business value

The workflow gives teams a consistent way to locate quality gaps, prioritize issue resolution, and review readiness before submission. Reported measures describe the project analysis, not clinical outcomes.

## Dashboard preview

![Clinical Data Quality Monitoring Dashboard](https://public.tableau.com/views/ClinicalDataQualityMonitoringDashboard/Dashboard1.png?:showVizHome=no)

[Open the interactive Tableau dashboard](https://public.tableau.com/app/profile/vaishnavi.amruthala8328/viz/ClinicalDataQualityMonitoringDashboard/Dashboard1)

## Project files

- [Tableau dashboard workbook](tableau/Clinical_Data_Liaison_Dashboard.twb)
- [Excel source workbook](data/Clinical_Data_Liaison_LNHS_Workbook.xlsx)

The Tableau workbook references the original local source path. If Tableau prompts for a missing source, connect it to the included Excel workbook in `data/`.
