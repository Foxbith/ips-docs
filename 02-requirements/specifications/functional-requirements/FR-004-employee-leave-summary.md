# FR-004: Employee Leave Summary (Late, Sick, Vacation)

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-004
title: "Employee Leave Summary (Late, Sick, Vacation)"
category: "Functional"
subcategory: "Employee Management, Leave Management, Reporting"
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
**I want** to view a summary of my (or my team's) late arrivals, sick leave, and vacation leave
**So that** I can track my leave balances and understand my attendance history.

---

## Detailed Description

The system shall display and summarize an employee's records for late arrivals, sick leave, and vacation leave. This summary should be accessible to both employees (for their own records) and their supervisors (for their direct reports). It should clearly distinguish between different types of leave and provide relevant details like dates and durations.

---

## Acceptance Criteria

- [ ] The system displays a breakdown of an employee's late arrivals, including dates and durations for each instance.
- [ ] The system displays a summary of sick leave taken, including dates and durations for each instance.
- [ ] The system displays a summary of vacation leave taken, including dates and durations for each instance.
- [ ] The system clearly distinguishes between different types of leave (e.g., sick leave, vacation leave, late arrival).
- [ ] Employees can view their own comprehensive leave summaries.
- [ ] Supervisors can view the comprehensive leave summaries of their direct reports.
- [ ] The summary views should be filterable by date range.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Employee Leave Dashboard, Supervisor Dashboard |
| User Flow | User navigates to Leave Summary -> Selects date range/employee (if supervisor) -> Views summary |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Aggregation | Leave data will be aggregated and categorized for summary display. |
| BR2 | Access Control | Access to leave summaries is restricted based on user role (employee vs. supervisor hierarchy). |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Employee ID | String | Yes | Existing Employee | Links to employee profile. |
| Leave Type | String | Yes | "Late", "Sick Leave", "Vacation Leave" | Type of leave or attendance exception. |
| Start Date | Date | Yes | Valid Date | Start date of leave/late incident. |
| End Date | Date | Yes | Valid Date (after Start Date) | End date of leave/late incident. |
| Duration | Decimal | Yes | Calculated | Duration of the leave/late incident in hours or days. |

---

## Dependencies

### Prerequisite Requirements
- FR-002 - Employee Time-Attendance - Clocking In/Out (for late arrivals data)
- FR-006 - Leave Request and Approval Workflow (for sick and vacation leave data)

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.4 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- Definitions for "sick leave" and "vacation leave" will be established within the system's configuration (FR-008).

**Open Questions:**
- [ ] How are partial days of leave handled?
- [ ] Are there different types of sick or vacation leave (e.g., paid vs. unpaid)?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
