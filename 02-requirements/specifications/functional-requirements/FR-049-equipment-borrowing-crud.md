# FR-049: Teaching Equipment Borrowing Request Management - CRUD

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-049
title: "Teaching Equipment Borrowing Request Management - CRUD"
category: "Functional"
subcategory: "Stationery Management, Workflow Management"
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

**As an** authorized staff member
**I want** to create, modify, or cancel teaching equipment borrowing requests
**So that** I can manage my equipment needs efficiently.

---

## Detailed Description

The system shall allow authorized users to add new borrowing requests for teaching equipment, modify existing requests (e.g., change dates or quantities of requested items, as long as it's still pending approval), and cancel requests. This functionality ensures flexibility in managing equipment needs.

---

## Acceptance Criteria

- [ ] Authorized users can create new borrowing requests, specifying the desired equipment (FR-044), quantity, preferred borrow date, and expected return date, regardless of current stock levels.
- [ ] Authorized users can modify their own pending borrowing requests (e.g., change dates, adjust quantities of items).
- [ ] Authorized users can cancel their own pending or approved borrowing requests.
- [ ] The system performs data validation on request details (e.g., valid dates, valid equipment).
- [ ] The system prevents modification of requests that are already approved and in use, or completed.
- [ ] The system provides an audit trail for all additions, modifications, and cancellations of borrowing requests, including who performed the action and when.
- [ ] Upon successful creation, modification, or cancellation, appropriate notifications are sent (e.g., to approvers, to the requester).

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Equipment Borrowing Request Form, My Requests Dashboard |
| User Flow | User navigates to request form -> Fills details -> Submits -> User views/modifies/cancels requests |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Authorization | Only the requester or an administrator can modify/cancel a request. |
| BR2 | Status-based Modification | Requests can only be modified if their status allows it (e.g., pending approval). |
| BR3 | Zero-Stock Requests | The system must allow users to create borrowing requests for equipment even if the current stock is zero. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Request ID | String | Yes | Unique | Unique identifier for the borrowing request. |
| Requester ID | String | Yes | Existing Employee ID | Employee submitting the request. |
| Borrow Date | Date | Yes | | Date the equipment is requested for. |
| Return Date | Date | Yes | After Borrow Date | Date the equipment is expected to be returned. |
| Requested Equipment | List of Objects | Yes | | List of Equipment ID and Quantity. |
| Status | String | Yes | Predefined list | (e.g., "Pending", "Approved", "Denied", "Canceled"). |

---

## Dependencies

### Prerequisite Requirements
- FR-044 - Teaching Equipment Information Management - Display Details (for selecting equipment).
- FR-048 - Teaching Equipment Borrowing Request Display (for viewing requests).

### Dependent Requirements
- FR-050 - Teaching Equipment Borrowing Request Search and Filter.
- FR-051 - Teaching Equipment Borrowing Request Approval.

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.7.2.2 |
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Row 21 regarding zero-stock withdrawal. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- Stock availability is checked during the approval/fulfillment stage (see FR-051), not at the time of request creation.
- Any modifications to approved requests will require re-approval.

**Open Questions:**
- [ ] Can users specify alternative equipment if their first choice is unavailable?
- [ ] What is the maximum duration for a borrowing request?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |
| 1.1 | 2025-11-30 | Gemini | Updated to allow requests for zero-stock items based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
