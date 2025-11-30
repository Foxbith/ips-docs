# FR-026: Asset Information Management - CRUD Operations & Status

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-026
title: "Asset Information Management - CRUD Operations & Status"
category: "Functional"
subcategory: "Asset Management, Data Management"
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

**As an** administrator or authorized staff member
**I want** to add, edit, delete, and update the status of asset data
**So that** asset records are comprehensive, up-to-date, and accurately reflect their condition.

---

## Detailed Description

The system shall provide authorized users with full CRUD (Create, Read, Update, Delete) operations for asset records. This includes the ability to add new assets, modify existing asset information (as detailed in FR-025), delete assets, and update their operational status (e.g., "Usable", "Damaged", "Broken", "In Repair", "Disposed").

---

## Acceptance Criteria

- [ ] Authorized users can add new asset records, including all comprehensive information fields (e.g., asset ID, serial number, specifications, vendor, images, and an initial status).
- [ ] Authorized users can modify any field within an existing asset's profile (e.g., update location, change specifications, replace image).
- [ ] Authorized users can update an asset's status from a predefined list (e.g., "Usable," "Damaged," "Broken," "In Repair," "Disposed").
- [ ] The system records the date of status change and the user who made the change for audit purposes.
- [ ] Authorized users can delete asset records.
- [ ] The system performs data validation during addition and modification processes to ensure data integrity and consistency.
- [ ] The system provides an audit trail for all additions, modifications, deletions, and status changes of asset data, recording who performed the action and when.
- [ ] Deletion of an asset record prompts for confirmation and may involve soft-deletion or archiving for historical purposes.
- [ ] Role-based permissions are enforced to restrict access to CRUD operations and status changes based on the user's level of authority.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Asset Management Dashboard, Asset Detail Edit Form |
| User Flow | Admin navigates to asset list -> Selects an asset / Clicks "Add New" -> Performs CRUD operation / Status update -> Confirms changes |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Validation | All input fields for asset data must be validated against predefined rules and formats (e.g., uniqueness of serial number, valid dates). |
| BR2 | Audit Log | Every CRUD operation and status change on asset data must be logged with user and timestamp. |
| BR3 | Data Integrity | Deletion of an asset record should consider cascading effects on related data (e.g., maintenance history). |
| BR4 | Status Transitions | Certain status changes may only be allowed from specific prior statuses. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| (All fields from FR-025) | | | | |
| Action Type | String | Yes | "Create", "Update", "Delete", "Status Change" | Type of operation performed. |
| Performed By | String | Yes | Existing User ID | User who performed the operation. |
| Timestamp | DateTime | Yes | | Date and time of the operation. |
| Previous Status | String | No | Predefined list | Previous status before change. |
| New Status | String | Yes | Predefined list | New status after change. |

---

## Dependencies

### Prerequisite Requirements
- FR-024 - Asset Master Data Configuration (for types, brands, vendors, locations).
- FR-025 - Asset Information Management - Display Details.

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md | Section 2.1.4.3, 2.1.4.4 |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- "Deleting" an asset record will likely involve a soft-delete mechanism or archiving to preserve historical records for auditing or inventory purposes.
- The list of possible asset statuses will be comprehensive and configurable (FR-024).

**Open Questions:**
- [ ] Are there specific roles or permissions required for each CRUD operation (e.g., separate roles for adding vs. deleting assets)?
- [ ] How will asset images be managed (e.g., storage location, file size limits)?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
