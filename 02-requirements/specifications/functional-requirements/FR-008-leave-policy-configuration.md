# FR-008: Leave Policy Configuration

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-008
title: "Leave Policy Configuration"
category: "Functional"
subcategory: "Employee Management, System Administration"
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

**As a** system administrator or HR manager
**I want** to configure various leave policies and rules
**So that** the system accurately reflects the company's official leave regulations.

---

## Detailed Description

The system shall provide administrators with the ability to define and configure various leave policies. This includes setting the maximum number of leave days per period, consecutive leave day limits, defining different leave types (sick, vacation, special, maternity, marriage, bereavement, etc.), setting normal working hours, and configuring "Cut Late" rules and public holidays.

---

## Acceptance Criteria

- [ ] Administrators can define different types of leave (e.g., Sick Leave, Vacation Leave, Special Leave, Maternity Leave, Marriage Leave, Bereavement Leave, Other Leave).
- [ ] For each defined leave type, administrators can configure rules such as:
    - [ ] Maximum number of days allowed per defined period (e.g., per month, per year, per academic year).
    - [ ] Maximum number of consecutive days allowed for a single leave request.
    - [ ] Eligibility criteria (e.g., based on employee tenure or employment status).
- [ ] Administrators can set and modify the normal working hours (e.g., daily clock-in and clock-out times).
- [ ] Administrators can configure "Cut Late" rules, including grace periods for late arrivals before being marked as late.
- [ ] Administrators can define and manage a list of public holidays, which impact attendance and leave calculations.
- [ ] The system provides a mechanism to apply these policies to different groups of employees if needed.
- [ ] All changes to leave policies are logged for audit purposes.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Admin Settings -> Leave Policy Configuration |
| User Flow | Administrator navigates to settings -> Configures leave types and rules -> Saves changes |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Policy Enforcement | Configured policies must be automatically enforced by the leave request and time-attendance modules. |
| BR2 | Customization | Policies should be flexible enough to accommodate various organizational needs. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Policy Name | String | Yes | Unique | Name of the leave policy. |
| Leave Type | String | Yes | Unique per policy | Name of the leave type (e.g., "Sick Leave"). |
| Max Days | Number | Yes | Positive integer | Maximum days for this leave type. |
| Max Consecutive Days | Number | No | Positive integer | Maximum consecutive days. |
| Time Period | String | Yes | "Monthly", "Annually", "Academic Year" | Period for which max days apply. |
| Normal Clock-in | Time | Yes | Valid Time | Standard clock-in time. |
| Normal Clock-out | Time | Yes | Valid Time | Standard clock-out time. |
| Cut Late Grace Period | Number | No | Non-negative integer | Minutes of grace period for lateness. |
| Public Holiday Date | Date | Yes | Valid Date | Date of a public holiday. |
| Public Holiday Name | String | Yes | | Name of the public holiday. |

---

## Dependencies

### Prerequisite Requirements
- FR-002 - Employee Time-Attendance - Clocking In/Out (for normal working hours and cut late rules).
- FR-006 - Leave Request and Approval Workflow (for applying leave type rules).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.8 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- "Academic Year" will be a configurable start and end date for the year.
- The system will be able to apply different policies to different employee groups if required by future needs.

**Open Questions:**
- [ ] What is the exact definition of "Cut Late"? Is it a grace period or a specific time past which an employee is marked late?
- [ ] How are changes to policies handled for in-progress leave requests?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
