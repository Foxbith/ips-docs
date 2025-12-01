# FR-017: Employee Employment Status Management

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-017
title: "Employee Employment Status Management"
category: "Functional"
subcategory: "Employee Management, Data Management"
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

**As an** HR administrator
**I want** to be able to adjust an employee's employment status
**So that** employee records accurately reflect their current employment relationship with the organization.

---

## Detailed Description

The system shall allow authorized HR administrators to modify an employee's employment status (e.g., "Current Employee," "Resigned," "Terminated," "On Leave"). This change in status should affect how the employee's data is displayed and processed within the system, potentially triggering other automated actions.

---

## Acceptance Criteria

- [ ] HR administrators can change an employee's employment status from a predefined and configurable list of statuses (e.g., "Current Employee," "Resigned," "Terminated," "On Leave", "Suspended").
- [ ] The system records the date of the status change and the user who made the change for audit purposes.
- [ ] Changing an employee's status (e.g., to "Resigned" or "Terminated") should trigger configurable automated system actions (e.g., restrict system access, update leave balances to 0, flag for archiving).
- [ ] The system allows for viewing and filtering employees based on their current and historical employment statuses.
- [ ] The current employment status is prominently visible on the employee's profile.
- [ ] The system prevents certain actions (e.g., leave requests) for employees with inappropriate statuses (e.g., "Resigned").

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Employee Profile -> Employment Details, HR Admin Employee List |
| User Flow | HR Admin navigates to employee profile -> Selects new status -> Confirms change |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Status Impact | Employment status changes must correctly influence system behavior and data visibility. |
| BR2 | Authorization | Only HR administrators with specific permissions can alter employment statuses. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Employee ID | String | Yes | Existing Employee | Links to employee profile. |
| Employment Status | String | Yes | Predefined list | Current employment status. |
| Status Change Date | Date | Yes | Valid Date | Date when the status was last changed. |
| Changed By | String | Yes | Existing User ID | User who initiated the status change. |

---

## Dependencies

### Prerequisite Requirements
- FR-015 - Employee Profile Management - CRUD Operations (to modify employee data).
- FR-016 - Employee Data Search and Filter (to filter by status).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.12.6 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The list of employment statuses will be comprehensive and cover all possible scenarios for the organization.
- Automated actions triggered by status changes (e.g., disabling accounts) will be defined.

**Open Questions:**
- [ ] What specific automated actions should occur when an employee's status changes to "Resigned" or "Terminated"?
- [ ] Are there specific dates (e.g., last working day) that need to be captured alongside the status change?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
