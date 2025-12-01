# FR-003: Employee Time-Attendance - Individual Clocking Summary

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-003
title: "Employee Time-Attendance - Individual Clocking Summary"
category: "Functional"
subcategory: "Employee Management, Reporting"
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

**As an** employee or supervisor
**I want** to view my (or my team's) summarized clock-in/out data
**So that** I can track attendance, working hours, and identify discrepancies.

---

## Detailed Description

The system shall display and summarize the individual clock-in/out data for each employee. This summary should provide clear visibility into an employee's attendance records, including clock-in/out times, total hours worked, and any attendance-related flags.

---

## Acceptance Criteria

- [ ] The system displays a list of daily clock-in/out records for a selected employee within a specified date range.
- [ ] The system provides a summary view (e.g., daily, weekly, monthly) of an employee's total working hours.
- [ ] The summary includes information such as clock-in time, clock-out time, total hours worked, and any attendance flags (e.g., late, early leave, missing entry).
- [ ] Supervisors can access and view the individual summaries of employees reporting to them.
- [ ] Employees can only view their own individual summaries.
- [ ] The summary view should be customizable by date range.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Employee Time-Attendance Dashboard, Supervisor Dashboard |
| User Flow | User navigates to Time-Attendance summary -> Selects date range/employee -> Views summary |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Aggregation | Clock-in/out data from FR-002 is aggregated for display. |
| BR2 | Access Control | Access to individual summaries is restricted based on user role (employee vs. supervisor). |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Employee ID | String | Yes | Existing Employee | Links to employee profile. |
| Date | Date | Yes | Valid Date | Date of attendance record. |
| Total Hours Worked | Decimal | Yes | Calculated from clock-in/out | Total working hours for the period. |
| Status Flags | List of Strings | No | Predefined values | e.g., "Late", "Early Leave", "Missing Clock-in", "Missing Clock-out". |

---

## Dependencies

### Prerequisite Requirements
- FR-002 - Employee Time-Attendance - Clocking In/Out

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.3 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The definition of "late" or "early leave" will be configured based on working hours.

**Open Questions:**
- [ ] What are the exact criteria for determining "late", "early leave", or other status flags?
- [ ] What level of detail is expected in the summary (e.g., granular breakdown by day, or just monthly totals)?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
