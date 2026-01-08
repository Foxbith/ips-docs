# FR-071: English Support Program (ESP) Management

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-071
title: "English Support Program (ESP) Management"
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

**As an** academic administrator
**I want** to manage English Support Program (ESP) enrollment, payments, and teacher compensation
**So that** I can track student participation and process payments efficiently across terms.

---

## Detailed Description

The system shall provide comprehensive management for the English Support Program (ESP), which operates on a term-based schedule (3 terms per year). The program supports group classes (1 teacher : multiple students) for students in Year 3-9. The system tracks student enrollment, payment collection, and teacher compensation calculations.

---

## Acceptance Criteria

- [ ] System supports term-based structure:
  - Term 1: September, October, November
  - Term 2: December, January, February
  - Term 3: March, April, May
- [ ] System allows enrollment of multiple students per teacher/class group
- [ ] Student enrollment records include: student name/ID/class, payment date, receipt number, payment amount, notes
- [ ] System calculates teacher payment at 60% of monthly rate (default: 2,500 x 60% = 1,500 THB per student)
- [ ] Payment percentage and base amount are configurable
- [ ] System generates payment sheets separated by teacher
- [ ] System supports class levels Y3-Y9

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Academic Portal, ESP Module |
| User Flow | Select Term -> Add Teacher/Class -> Enroll Students -> Process Payments -> Generate Reports |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Teacher-Student Ratio | 1 teacher per multiple students (group class) |
| BR2 | Term Pricing | 7,500 THB per term per student |
| BR3 | Annual Pricing | 22,500 THB for full year (3 terms) |
| BR4 | Monthly Rate | 2,500 THB per month (term has 3 months) |
| BR5 | Teacher Payment | 60% of monthly rate = 1,500 THB per student per month |
| BR6 | Class Levels | Only Y3-Y9 students eligible |
| BR7 | Teacher Optional | Teacher can be assigned later (optional at creation) |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Program Type | String | Yes | "ESP" | Fixed value |
| Teacher ID | String | No | Existing Teacher | Can be assigned later |
| Term | String | Yes | Term 1/2/3 | Academic term |
| Class Group | String | Yes | Y3-Y9 | Grade level group |
| Student List | Array | Yes | Valid students | Enrolled students |
| Student ID | String | Yes | Existing Student | Per student record |
| Student Name | String | Yes | From profile | Auto-populated |
| Student Class | String | Yes | From profile | Grade level |
| Payment Date | Date | Yes | Valid Date | Per student |
| Receipt Number | String | Yes | Unique | Per student |
| Payment Amount | Number | Yes | > 0 | Amount paid |
| Notes | String | No | - | Additional notes |
| Base Monthly Rate | Number | Yes | Default 2,500 | Configurable |
| Teacher Percentage | Number | Yes | Default 60% | Configurable |

---

## Report Requirements

| Report | Description |
|--------|-------------|
| ESP Student Report | All students enrolled in ESP |
| ESP by Teacher | Students grouped by assigned teacher |
| ESP by Class Level | Students grouped by grade level |
| ESP Income - All | Total income from ESP fees |
| ESP Income - Date Range | Income within specified dates |
| ESP Income - Receipt | Income by receipt number |
| ESP Payment - All | Total payments made to teachers |
| ESP Payment - Monthly | Monthly teacher payment breakdown |

---

## Dependencies

### Prerequisite Requirements
- FR-001 - User Login via Google (for system access)
- Student Profile Management
- Teacher Profile Management

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Source Document | After School Requirements CSV | Section 2 - ESP |

---

## References

- **Source Document:** จัดทำระบบ After School ใหม่ - Requirement.csv

---

## Notes

**Assumptions:**
- Term dates are fixed annually
- Payment rates may be adjusted but defaults are as specified
- Teacher assignment can happen after initial enrollment

**Open Questions:**
- [ ] How to handle mid-term enrollments?
- [ ] Refund policy for withdrawals?
- [ ] Integration with accounting system?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2026-01-08 | Claude | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
