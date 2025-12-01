# FR-059: Dashboard - Leave Summary Display

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-059
title: "Dashboard - Leave Summary Display"
category: "Functional"
subcategory: "Reporting, Employee Management"
phase: 1
contract_ref: "CC20240711001"
version: "1.0"
status: "Draft"
priority: "Must Have"
created: "2025-11-30"
last_modified: "2025-11-30"
author: "Gemini"
approved_by: "[PENDING]"
```

---

## Requirement Statement

**As a** manager or administrator
**I want** to view a summarized overview of employee leave data
**So that** I can quickly grasp overall attendance and leave trends.

---

## Detailed Description

The system shall provide a dashboard that displays summarized employee leave data in various formats. This includes aggregated clock-in/out summaries (from FR-003) and detailed breakdowns of late arrivals, sick leave, and vacation leave (from FR-004), presented in an easy-to-understand visual format.

---

## Acceptance Criteria

- [ ] The dashboard displays a summary of overall employee attendance (e.g., total working hours, average lateness, absent days) for a selected period.
- [ ] The dashboard displays a summary of different leave types taken (e.g., total sick days, total vacation days, total special leave days) for a selected period.
- [ ] Data can be presented in various interactive formats such as charts, graphs (e.g., pie charts for leave types, bar charts for lateness trends), or aggregated tables.
- [ ] The dashboard allows for filtering by date range (e.g., monthly, quarterly, custom), department, or employee group.
- [ ] Data is accurately drawn and aggregated from individual employee clock-in/out records (FR-003) and leave summaries (FR-004).
- [ ] Access to the dashboard is restricted to authorized managers and administrators based on their roles and reporting lines.
- [ ] The dashboard is updated in near real-time or at regular intervals (e.g., daily).

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Main Dashboard, Analytics Page |
| User Flow | Manager logs in -> Navigates to dashboard -> Views leave summaries -> Applies filters |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Aggregation | Data must be correctly aggregated from underlying detailed records. |
| BR2 | Authorization | Access to dashboard data is strictly controlled by user permissions. |
| BR3 | Data Presentation | Summarized data should be easy to interpret visually. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Period | Date Range | Yes | Valid Dates | Timeframe for the summary. |
| Employee Group | String | No | Existing Groups | Filter for specific departments or teams. |
| Summary Metrics | Various | Yes | | Aggregated counts, totals, averages for attendance and leave. |

---

## Dependencies

### Prerequisite Requirements
- FR-003 - Employee Time-Attendance - Individual Clocking Summary.
- FR-004 - Employee Leave Summary (Late, Sick, Vacation).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.9.1 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The system will provide basic charting and graphing capabilities for data visualization.
- The definition of "various formats" implies common chart types (bar, pie, line).

**Open Questions:**
- [ ] What specific types of charts or graphs are preferred for presenting this data?
- [ ] What is the exact level of detail expected in the summary (e.g., per employee, per department, overall)?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
