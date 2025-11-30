# FR-009: Academic Year Management and Leave Reset

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-009
title: "Academic Year Management and Leave Reset"
category: "Functional"
subcategory: "Employee Management, System Administration, Academic Management"
phase: 1
contract_ref: "CC20240711001"
version: "1.1"
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
**I want** to define and manage academic years, and configure leave balances to reset based on these academic year cycles
**So that** employee leave entitlements are correctly managed for each academic period.

---

## Detailed Description

The system shall allow authorized personnel to define and manage Academic Years, which may span across calendar years (e.g., August 2025 to June 2026). At the end of each defined Academic Year, the system must automatically reset specified employee leave balances (e.g., vacation, sick leave) for the new year. An authorized user must have the ability to manually trigger the closing of an academic year to initiate the reset process for the subsequent academic year.

---

## Acceptance Criteria

- [ ] Administrators can define the start and end dates of Academic Years.
- [ ] The system must correctly handle Academic Years that span across two different calendar years (e.g., start date in one year and end date in the next).
- [ ] The user interface for setting dates must be clear and prevent confusion between calendar years and academic years.
- [ ] The system automatically resets specified leave balances (e.g., vacation days, sick days) for all employees at the beginning of a new Academic Year, based on configured policies (FR-008).
- [ ] An authorized user can manually initiate the "closing" of an Academic Year, which triggers the leave balance reset for the next year.
- [ ] The system provides an audit log of all leave balance resets, including the date, affected employees, their old and new balances, and the user who initiated the reset.
- [ ] The system ensures that all leave taken in the previous Academic Year is correctly accounted for before the reset occurs.
- [ ] The system provides warnings or confirmations before a manual Academic Year closure and reset operation.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Admin Settings -> Academic Year Settings |
| User Flow | Administrator defines Academic Year start and end dates -> Initiates year closure -> System performs reset |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Cross-Calendar Year | An Academic Year is defined by a start date and an end date, which may fall in different calendar years. |
| BR2 | Reset Timing | Leave balances are reset at the start of a new Academic Year. |
| BR3 | Authorization | Only authorized personnel can manage Academic Years and initiate resets. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Academic Year ID | String | Yes | Unique | Identifier for the academic year (e.g., "2025-2026"). |
| Start Date | Date | Yes | Valid Date | Start date of the academic year. |
| End Date | Date | Yes | Valid Date (after Start Date) | End date of the academic year. |
| Reset Trigger | String | Yes | "Automatic", "Manual" | How the reset is initiated. |
| Reset Date | Date | No | Valid Date | Date the reset occurred. |
| Initiated By | String | No | Existing User ID | User who initiated a manual reset. |

---

## Dependencies

### Prerequisite Requirements
- FR-008 - Leave Policy Configuration (to define the types of leave and their entitlements).
- Employee records with current leave balances.

### Dependent Requirements
- FR-004 - Employee Leave Summary (to reflect updated balances).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.9 |
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Rows 2 & 3 regarding errors in setting academic year. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The concept of an "academic year" is clearly defined by the school.
- Any carry-over rules for unused leave will be managed within FR-008 or this feature.

**Open Questions:**
- [ ] What specific leave types are subject to reset (e.g., only vacation, or sick leave as well)?
- [ ] Are there any rules for carrying over unused leave days to the next round?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |
| 1.1 | 2025-11-30 | Gemini | Updated to clarify Academic Year handling based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
