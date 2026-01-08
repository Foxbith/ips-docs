# FR-072: Summer School Management

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-072
title: "Summer School Management"
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
**I want** to manage Summer School enrollment and track VAN service usage
**So that** I can organize summer programs and generate enrollment/payment reports.

---

## Detailed Description

The system shall provide management for Summer School programs, which typically run for approximately 1 month during June-July. The program supports group classes (1 teacher : multiple students) for students in K1-Y6. The system also tracks optional VAN (transportation) service enrollment and payments. Pricing varies annually.

---

## Acceptance Criteria

- [ ] System allows creation of Summer School programs with year designation (YYYY)
- [ ] System supports date range definition (start date - end date, typically ~1 month)
- [ ] System allows enrollment of multiple students per class/teacher
- [ ] Student enrollment records include: student name/ID/class, payment date, receipt number, payment amount
- [ ] System tracks VAN service enrollment separately with its own payment tracking
- [ ] System supports adding new students (not in existing database) for Summer School
- [ ] System supports class levels K1-Y6
- [ ] Pricing is configurable per year

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Academic Portal, Summer School Module |
| User Flow | Create Program -> Set Dates/Price -> Enroll Students -> Track VAN -> Generate Reports |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Teacher-Student Ratio | 1 teacher per multiple students (group class) |
| BR2 | Duration | Approximately 1 month (June-July typically) |
| BR3 | Class Levels | K1-Y6 students eligible |
| BR4 | Variable Pricing | Price changes annually (configurable) |
| BR5 | Teacher Optional | Teacher can be assigned later |
| BR6 | External Students | System allows adding students not in main database |
| BR7 | VAN Service | Optional transportation service with separate tracking |
| BR8 | No Teacher Payment | Summer School does not have teacher payment tracking |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Program Type | String | Yes | "Summer School" | Fixed value |
| Program Year | Number | Yes | Valid Year | e.g., 2026 |
| Start Date | Date | Yes | Valid Date | Program start |
| End Date | Date | Yes | > Start Date | Program end |
| Program Price | Number | Yes | > 0 | Annual variable price |
| Teacher ID | String | No | Existing Teacher | Can be assigned later |
| Class Group | String | Yes | K1-Y6 | Grade level group |
| Student List | Array | Yes | - | Enrolled students |
| Student ID | String | No | - | May be new student |
| Student Name | String | Yes | - | Manual entry allowed |
| Student Class | String | Yes | K1-Y6 | Grade level |
| Payment Date | Date | Yes | Valid Date | Per student |
| Receipt Number | String | Yes | Unique | Per student |
| Payment Amount | Number | Yes | > 0 | Amount paid |
| VAN Service | Boolean | No | Yes/No | Using VAN? |
| VAN Payment Date | Date | Conditional | If VAN=Yes | VAN payment date |
| VAN Receipt Number | String | Conditional | If VAN=Yes | VAN receipt |
| VAN Amount | Number | Conditional | If VAN=Yes | VAN fee |
| Notes | String | No | - | Additional notes |

---

## Report Requirements

| Report | Description |
|--------|-------------|
| Summer Student Report | All students enrolled in Summer School |
| Summer by Teacher | Students grouped by assigned teacher |
| Summer by Class Level | Students grouped by grade level |
| Summer Income - All | Total income from Summer School fees |
| Summer Income - Date Range | Income within specified dates |
| Summer Income - Receipt | Income by receipt number |
| VAN Service Report | Students using VAN service with payments |

---

## Dependencies

### Prerequisite Requirements
- FR-001 - User Login via Google (for system access)
- Student Profile Management (optional - can add new students)
- Teacher Profile Management

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Source Document | After School Requirements CSV | Section 3 - Summer School |

---

## References

- **Source Document:** จัดทำระบบ After School ใหม่ - Requirement.csv

---

## Notes

**Assumptions:**
- Summer School is a standalone program separate from regular academic year
- New students can be enrolled without full profile creation
- VAN service is optional and tracked separately

**Open Questions:**
- [ ] How to handle students who enroll mid-program?
- [ ] VAN service provider integration?
- [ ] Carry-over of student data from Summer School to regular enrollment?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2026-01-08 | Claude | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
