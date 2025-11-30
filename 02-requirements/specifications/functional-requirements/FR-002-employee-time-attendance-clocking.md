# FR-002: Employee Time-Attendance - Clocking In/Out

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-002
title: "Employee Time-Attendance - Clocking In/Out"
category: "Functional"
subcategory: "Employee Management"
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
**I want** to record my daily clock-in and clock-out times
**So that** my attendance and working hours can be accurately tracked.

---

## Detailed Description

The system shall allow employees (teachers and staff) to record their daily clock-in and clock-out times. It must also support the import of clock-in/out data from an external Finger Scan system.

---

## Acceptance Criteria

- [ ] Employees can manually record their clock-in and clock-out times within the system.
- [ ] The system can successfully import clock-in and clock-out data from a specified Finger Scan system.
- [ ] The imported data from the Finger Scan system is correctly associated with the respective employee records.
- [ ] The system handles potential discrepancies or errors during manual entry or finger scan import (e.g., duplicate entries, missing data).
- [ ] The system logs the source of the clocking data (manual or Finger Scan).

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Employee Portal, Time-Attendance Module |
| User Flow | Employee accesses Time-Attendance -> Enters clock-in/out -> Submits |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Source | Clock-in/out data can originate from manual entry or Finger Scan import. |
| BR2 | Personnel Type | Both teachers and staff must be able to use the time-attendance system. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Employee ID | String | Yes | Existing Employee | Links to employee profile. |
| Clock-in Time | DateTime | Yes | Valid Date/Time | Timestamp of clock-in. |
| Clock-out Time | DateTime | No | Valid Date/Time (after clock-in) | Timestamp of clock-out. |
| Data Source | String | Yes | "Manual", "Finger Scan" | Indicates how the record was created. |

---

## Dependencies

### Prerequisite Requirements
- FR-001 - User Login via Google (for system access)
- Employee Profile Management (for employee data)

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.2.1, 2.1.2.2 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The Finger Scan system provides a data export in a format compatible with the Intranet system (e.g., CSV, API).
- A mechanism for mapping Finger Scan IDs to internal Employee IDs will be provided.

**Open Questions:**
- [ ] What is the exact format of the Finger Scan data export?
- [ ] How frequently will Finger Scan data be imported?
- [ ] What are the specific requirements for manual time entry (e.g., web interface, kiosk)?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
