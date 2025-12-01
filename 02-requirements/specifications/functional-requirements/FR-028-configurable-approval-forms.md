# FR-028: Configurable Approval Forms

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-028
title: "Configurable Approval Forms"
category: "Functional"
subcategory: "Workflow Management, System Administration"
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

**As an** administrator
**I want** to create, edit, and delete various approval request forms
**So that** I can maintain a set of specific and relevant forms for different types of requests within the system.

---

## Detailed Description

The system shall provide administrators with the ability to create, edit, and delete up to 5 distinct approval request forms. This includes defining the fields, layout, and purpose of each form to support various types of internal requests beyond leave and off-site work, thereby streamlining different approval processes.

---

## Acceptance Criteria

- [ ] Administrators can create new approval request forms, defining their fields and properties.
- [ ] Administrators can edit existing approval request forms, modifying their fields, layout, title, and description.
- [ ] Administrators can delete existing approval request forms, with appropriate warnings if forms have associated pending requests or historical data.
- [ ] Administrators can configure up to 5 distinct approval request forms.
- [ ] Each form can have configurable fields, including:
    - [ ] Text input fields (single-line, multi-line)
    - [ ] Date pickers
    - [ ] Dropdown menus (with configurable options)
    - [ ] File upload fields
- [ ] Administrators can define the title, description, and instructions for each form.
- [ ] The configured forms are accessible and available for employees to fill out and submit.
- [ ] The system allows for defining the approval workflow for each form, potentially linking to the organizational hierarchy (FR-005) for routing.
- [ ] Administrators can preview the forms before making them active.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Admin Settings -> Form Builder/Manager |
| User Flow | Administrator navigates to form manager -> Creates/Edits form -> Defines fields and properties -> Saves/Publishes form |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Form Limit | The system must support a maximum of 5 distinct configurable forms. |
| BR2 | Approval Workflow | Each form can be associated with a specific approval workflow. |
| BR3 | Data Validation | Form fields must support configurable validation rules. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Form ID | String | Yes | Unique | Identifier for the form. |
| Form Name | String | Yes | Not Empty | Title of the form. |
| Form Description | Text | No | | Description/instructions for the form. |
| Fields | List of Objects | Yes | | Each object represents a form field with its type, label, options, and validation rules. |
| Approval Workflow ID | String | No | Existing Workflow | Link to an approval workflow. |

---

## Dependencies

### Prerequisite Requirements
- FR-005 - Organizational Structure and Job Position Management (for defining approval hierarchies).

### Dependent Requirements
- FR-029 - Approval Request Form Submission (uses these configured forms).

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.5.1 |
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Rows 8 & 35 regarding Purchasing Form. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The system will provide a user-friendly interface for building and configuring forms.
- File uploads within forms will be securely handled.

**Implementation Considerations:**
- One of the configurable forms should be designated as a "Purchasing Form". Based on UAT feedback (Rows 8 & 35), the "Product" field on this form should be a free-text input rather than a search selection from the existing product list. The backend should accept this free-text `productName` without requiring a `productID`.

**Open Questions:**
- [ ] What types of validation rules are needed for form fields (e.g., mandatory, number range, specific format)?
- [ ] Can forms be deactivated or archived?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |
| 1.1 | 2025-11-30 | Gemini | Added note on Purchasing Form behavior based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
