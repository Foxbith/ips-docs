# FR-006: Leave Request and Approval Workflow

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-006
title: "Leave Request and Approval Workflow"
category: "Functional"
subcategory: "Employee Management, Leave Management"
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
**I want** to request leave through a formal process with hierarchical approval
**So that** my leave requests are properly managed and approved by my supervisor(s).

---

## Detailed Description

The system shall provide a workflow for employees to submit leave requests. These requests must follow a predefined hierarchical approval process based on the organizational structure, ensuring that requests are routed to the appropriate supervisors for approval. Supervisors must be able to approve or reject requests.

---

## Acceptance Criteria

- [ ] Employees can submit new leave requests, specifying leave type, dates, and reasons.
- [ ] The system automatically routes the leave request to the employee's direct supervisor for initial approval.
- [ ] The system supports multi-level approval chains based on the defined organizational hierarchy (e.g., direct supervisor -> department head).
- [ ] Supervisors can view pending leave requests, approve them, or reject them with an optional reason.
- [ ] Employees receive notifications regarding the status of their leave requests (e.g., submitted, approved, rejected).
- [ ] The system updates the employee's leave balance upon approval of a leave request.
- [ ] The system maintains a history of all leave requests and their approval status.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Employee Leave Request Form, Supervisor Approval Dashboard |
| User Flow | Employee submits request -> Supervisor receives notification -> Supervisor reviews and acts on request -> Employee receives status update |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Approval Hierarchy | Leave requests must follow the approval hierarchy defined in the organizational structure. |
| BR2 | Leave Balance Update | Approved leave must deduct from the employee's available leave balance. |
| BR3 | Rejection Reason | Supervisors should be able to provide a reason for rejecting a leave request. |
| BR4 | No Self-Approval | The system must prevent a user from approving their own leave request, enforcing the rule from FR-005. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Employee ID | String | Yes | Existing Employee | Submitting employee. |
| Leave Type | String | Yes | Predefined list (e.g., Sick, Vacation) | Type of leave requested. |
| Start Date | Date | Yes | Valid Date | Start date of the requested leave. |
| End Date | Date | Yes | Valid Date (>= Start Date) | End date of the requested leave. |
| Reason | Text | Yes | Min 10 characters | Explanation for the leave request. |
| Status | String | Yes | "Pending", "Approved", "Rejected" | Current status of the request. |
| Approver ID | String | No | Existing Employee | ID of the employee who approved/rejected the request. |
| Approval Date | DateTime | No | Valid Date/Time | Timestamp of approval/rejection. |
| Rejection Reason | Text | No | | Reason provided if the request is rejected. |

---

## Dependencies

### Prerequisite Requirements
- FR-005 - Organizational Structure and Job Position Management (for approval hierarchy).
- FR-008 - Leave Policy Configuration (for defining leave types and rules).

### Dependent Requirements
- FR-004 - Employee Leave Summary (for reporting approved leave).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.6 |
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Row 22 regarding self-approval. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The system will define clear roles and permissions for who can approve different types of leave.

**Open Questions:**
- [ ] What happens if an approver is unavailable? Is there an escalation process?
- [ ] Are there different approval workflows for different leave types?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |
| 1.1 | 2025-11-30 | Gemini | Added 'No Self-Approval' rule based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
