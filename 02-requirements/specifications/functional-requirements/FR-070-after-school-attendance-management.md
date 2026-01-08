# FR-070: After School - Attendance Management

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-070
title: "After School - Attendance Management"
category: "Functional"
subcategory: "Academic Programs"
phase: 2
contract_ref: "CC20240711001"
version: "1.0"
status: "Draft"
priority: "Must Have"
created: "2026-01-08"
last_modified: "2026-01-08"
author: "Claude"
approved_by: "[PENDING]"
```

---

## Requirement Statement

**As a** teacher
**I want** to record student attendance for After School tutoring sessions
**So that** I can track student learning hours and generate attendance sheets for payment processing.

---

## Detailed Description

The system shall provide attendance tracking for After School individual tutoring programs (1 teacher : 1 student). Teachers can create and manage attendance sheets that track student learning hours across full courses (12 hours) or partial courses. The system supports split payment scenarios with separate attendance sheets.

---

## Acceptance Criteria

- [ ] System allows creation of After School attendance records with required fields (student, teacher, subject, schedule)
- [ ] System supports three course types:
  - Full course: 12 hours (single attendance sheet)
  - Full course with split payment: 12 hours divided into 2 x 6 hours (2 attendance sheets)
  - Partial course: Custom hours (e.g., 5 hours)
- [ ] Teachers can select class days from Mon/Wed/Fri (individually or combined)
- [ ] System displays warning when student has schedule conflicts with other subjects (but allows continuation)
- [ ] Attendance sheet displays: program type, receipt date, receipt number, student info, subject, teacher, schedule, total hours
- [ ] System generates attendance sheets in printable format

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Academic Portal, After School Module |
| User Flow | Create Attendance -> Select Student/Teacher/Subject -> Set Schedule -> Define Course Type -> Save |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Teacher-Student Ratio | 1 teacher per 1 student for After School program |
| BR2 | Class Days | Classes only on Monday, Wednesday, Friday |
| BR3 | Schedule Conflict | System warns but allows continuation when student has overlapping schedules |
| BR4 | Split Payment | Full course can be split into 2 attendance sheets of 6 hours each |
| BR5 | Course Hours | Full course = 12 hours; partial course = user-defined hours |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Program Type | String | Yes | "After School" | Fixed value |
| Receipt Date | Date | Yes | Valid Date | Payment receipt date |
| Receipt Number | String | Yes | Unique | Payment receipt reference |
| Student ID | String | Yes | Existing Student | Links to student profile |
| Student Name | String | Yes | From profile | Auto-populated |
| Student Class | String | Yes | From profile | Grade level |
| Parent Contact | String | Yes | From profile | Emergency contact |
| Subject | String | Yes | Valid Subject | Course subject |
| Teacher ID | String | Yes | Existing Teacher | Links to teacher profile |
| Class Days | Array | Yes | Mon/Wed/Fri | Selected days |
| Course Type | String | Yes | Full/Split/Partial | Course structure |
| Total Hours | Number | Yes | > 0 | Total learning hours |
| Attendance Records | Array | No | Valid entries | Individual session records |

---

## Dependencies

### Prerequisite Requirements
- FR-001 - User Login via Google (for system access)
- Student Profile Management
- Teacher Profile Management
- Subject/Course Management

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Source Document | After School Requirements CSV | Section 1 - After School |

---

## References

- **Source Document:** จัดทำระบบ After School ใหม่ - Requirement.csv

---

## Notes

**Assumptions:**
- Student and teacher profiles already exist in the system
- Receipt information comes from the payment/finance module
- Class schedule is fixed to Mon/Wed/Fri only

**Open Questions:**
- [ ] Integration with payment/finance module for receipt data?
- [ ] Notification system for schedule conflicts?
- [ ] Mobile access for teachers to record attendance?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2026-01-08 | Claude | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
