# FR-010: Off-site Work Request and Approval (Present Form)

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-010
title: "Off-site Work Request and Approval (Present Form)"
category: "Functional"
subcategory: "Employee Management, Workflow Management"
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

**As an** employee
**I want** to request approval for working off-site (Present Form)
**So that** my off-site work is formally recognized and approved without affecting my leave balance.

---

## Detailed Description

The system shall provide a mechanism for employees to submit requests for working off-site, referred to as a "Present Form." These requests must follow the established approval hierarchy, similar to leave requests (FR-006), but critically, approved off-site work days will be recorded as work days and will not be deducted from the employee's leave balances.

---

## Acceptance Criteria

- [ ] Employees can submit new off-site work requests, specifying dates, times (if applicable), and reasons for working off-site.
- [ ] The system automatically routes off-site work requests through the defined approval hierarchy (similar to FR-006).
- [ ] Supervisors can view pending off-site work requests, approve them, or reject them with a reason.
- [ ] Approved off-site work days are recorded in the system as working days and do not deduct from any leave balances.
- [ ] Employees receive notifications regarding the status of their off-site work requests (e.g., submitted, approved, rejected).
- [ ] The system provides a clear distinction in records between approved off-site work and actual leave.
- [ ] Off-site work requests should allow for partial day requests.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Employee Off-site Work Request Form, Supervisor Approval Dashboard |
| User Flow | Employee submits request -> Supervisor receives notification -> Supervisor reviews and acts -> Employee receives status update |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Approval Hierarchy | Off-site work requests must follow the approval hierarchy defined in the organizational structure (FR-005). |
| BR2 | No Leave Deduction | Approved off-site work days must not be deducted from any employee leave balances. |
| BR3 | Status Tracking | The status of off-site work requests must be tracked and communicated. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Employee ID | String | Yes | Existing Employee | Submitting employee. |
| Request Type | String | Yes | "Off-site Work" | Type of request. |
| Start Date | Date | Yes | Valid Date | Start date of off-site work. |
| End Date | Date | Yes | Valid Date (>= Start Date) | End date of off-site work. |
| Reason | Text | Yes | Min 10 characters | Explanation for working off-site. |
| Status | String | Yes | "Pending", "Approved", "Rejected" | Current status of the request. |
| Approver ID | String | No | Existing Employee | ID of the employee who approved/rejected. |
| Approval Date | DateTime | No | Valid Date/Time | Timestamp of approval/rejection. |
| Rejection Reason | Text | No | | Reason if rejected. |

---

## Dependencies

### Prerequisite Requirements
- FR-005 - Organizational Structure and Job Position Management (for approval hierarchy).
- FR-006 - Leave Request and Approval Workflow (reused workflow logic).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.10 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- "Present Form" is distinct from various leave types and represents a legitimate working status.
- The system will distinguish between "off-site work" and regular "work from office" in attendance records.

**Open Questions:**
- [ ] Is there a limit to how many off-site work days an employee can request?
- [ ] Are there specific times when off-site work is not allowed or requires higher-level approval?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
