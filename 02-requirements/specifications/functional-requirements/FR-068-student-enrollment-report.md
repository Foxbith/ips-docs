# FR-068: Student Academic Enrollment Report

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-068
title: "Student Academic Enrollment Report"
category: "Functional"
subcategory: "Reporting, Academic Management"
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

**As an** administrator or academic staff
**I want** to generate a report showing which subjects and classes a student is enrolled in
**So that** I can track student schedules and academic progress.

---

## Detailed Description

The system shall provide a report that, for a selected student, lists all the academic programs, subjects, and classes they are enrolled in (e.g., After School, Intervention, ESP). The report should be exportable to PDF and include relevant details like course names and receipt dates for any associated payments.

---

## Acceptance Criteria

- [ ] Users can select a student and generate a report of their academic enrollments.
- [ ] The report lists all subjects, classes, and special programs (After School, Intervention, ESP) the student is enrolled in.
- [ ] The report can be exported to PDF format.
- [ ] The exported PDF report includes a "Receipt Date" column for any payment-related enrollments.
- [ ] The report is structured into different sections or can be generated for different types of enrollment (e.g., a separate PDF for "fix_course", "summer", "term").
- [ ] The system also allows for exporting a separate "Payment PDF" related to these enrollments.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Student Profile -> Academic Enrollments -> Export Report Button |
| User Flow | User navigates to a student's profile -> Goes to their academic section -> Clicks "Export Report" -> Selects report type (e.g., Info, Payment) -> System generates and downloads PDF. |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Aggregation | The report must accurately aggregate all enrollment data for the selected student. |
| BR2 | PDF Formatting | The exported PDFs must be clearly formatted and organized. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Student ID | String | Yes | Existing Student ID | The student for whom the report is generated. |
| Program/Class Name | String | Yes | | Name of the enrolled item. |
| Enrollment Type | String | Yes | | e.g., "fix_course", "summer", "term". |
| Receipt Date | Date | No | | Date of payment receipt, if applicable. |

---

## Dependencies

### Prerequisite Requirements
- FR-018 - Student Profile Management - Display Comprehensive Information.
- FR-055 - After School/Intervention/ESP Class Booking Management.

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Rows 31 & 38 regarding the student enrollment report and receipt date column. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The system captures payment and receipt date information for academic enrollments.
- The different enrollment types ("fix_course", "summer", "term") are defined and managed within the system.

**Open Questions:**
- [ ] What specific fields should be included in the "Information PDF" versus the "Payment PDF"?
- [ ] Is there a need to filter the report by academic year?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
