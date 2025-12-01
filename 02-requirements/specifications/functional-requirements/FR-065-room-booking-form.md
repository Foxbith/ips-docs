# FR-065: Room Booking Form

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-065
title: "Room Booking Form"
category: "Functional"
subcategory: "Workflow Management, Resource Management"
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

**As a** user
**I want** to request to book a room using a specific form with rules for availability and overlaps
**So that** school facilities can be managed and booked efficiently.

---

## Detailed Description

The system shall provide a dedicated "Room Booking Form" that allows users to request the use of school rooms. The form must include a dropdown list of specific, unique rooms and an option for "Other". The system must enforce business rules to prevent double-booking or overlapping times for the specific, unique rooms, while allowing overlaps for the "Other" category.

---

## Acceptance Criteria

- [ ] The system provides a "Room Booking Form" for users to submit requests.
- [ ] The form includes a "Room" field, which is a dropdown list.
- [ ] The dropdown list contains a predefined list of specific rooms (e.g., Auditorium, Canteen, Meeting Room) and a final option for "Other".
- [ ] The system prevents the approval of a booking if the requested time slot for a specific room (not "Other") overlaps with an already approved booking for the same room.
- [ ] The system allows multiple bookings for the "Other" room category to have overlapping time slots.
- [ ] The conflict resolution rule is "first to be approved": when a booking is approved for a specific room and time, any other pending requests for the same room and an overlapping time slot are automatically canceled or flagged as rejected.
- [ ] The form follows the standard approval workflow (submission, approval/denial, notifications) as defined in FR-029 and FR-030.
- [ ] Users must specify a start time and an end time for the booking.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Room Booking Form, Room Booking Calendar/Schedule View |
| User Flow | User fills out Room Booking Form -> Submits -> Approver receives and approves -> System validates for conflicts -> Confirms booking or rejects conflicting requests. |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Unique Room Constraint | Specific rooms (e.g., Auditorium, Canteen) cannot have overlapping approved bookings. |
| BR2 | "Other" Room Exception | Bookings for the "Other" room category are exempt from the overlap constraint. |
| BR3 | First-Approved Wins | For conflicting requests, the first one to receive "Approved" status claims the time slot. |
| BR4 | Backend Validation | The validation for overlapping bookings must be handled on the backend upon approval, not just on the frontend. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Booking ID | String | Yes | Unique | Unique identifier for the room booking. |
| Requester ID | String | Yes | Existing Employee ID | Employee who is requesting the room. |
| Room Name | String | Yes | From predefined list | The specific room being requested. |
| Start Time | DateTime | Yes | | Start date and time of the booking. |
| End Time | DateTime | Yes | After Start Time | End date and time of the booking. |
| Status | String | Yes | Predefined list | "Pending", "Approved", "Rejected", "Canceled". |

---

## Dependencies

### Prerequisite Requirements
- FR-028 - Configurable Approval Forms (to provide the form framework).
- FR-029 - Approval Request Form Submission and Tracking.
- FR-030 - Approval Request Form Approval/Rejection.

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Rows 24 & 25, defining the room booking form, dropdown, and overlap rules. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The list of specific rooms is configurable by an administrator.
- The approval workflow for room bookings is similar to other form-based requests.

**Open Questions:**
- [ ] Should there be a visual calendar view to see room availability before booking?
- [ ] How are recurring bookings handled?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
