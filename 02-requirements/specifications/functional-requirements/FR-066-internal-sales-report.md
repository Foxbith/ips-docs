# FR-066: Daily Internal Order Sales Report (PDF)

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-066
title: "Daily Internal Order Sales Report (PDF)"
category: "Functional"
subcategory: "Reporting, Sales Management"
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

**As a** store manager or administrator
**I want** to generate a daily PDF sales report that details internal orders and stock movements
**So that** I can track internal consumption and reconcile inventory.

---

## Detailed Description

The system shall provide the ability to generate a daily sales report in PDF format. This report will specifically focus on "Internal Orders" and provide a summary of stock movements for products included in those orders within a selected date range. The report should be downloadable from the product inventory page.

---

## Acceptance Criteria

- [ ] A "Download PDF" button is available on the product inventory page.
- [ ] Users can filter the data for the report by a date range.
- [ ] The generated PDF report is based on the data currently visible in the UI, filtered by the selected date range.
- [ ] The PDF report includes the following columns for each product:
    - [ ] **productID**: The internal inventory ID of the product.
    - [ ] **code (SKU)**: The product's SKU or code.
    - [ ] **productName**: The name of the product.
    - [ ] **Price**: The price per unit of the product.
    - [ ] **CN (Cancelled/Returned)**: Total quantity of the product from cancelled or returned orders within the date range.
    - [ ] **Internal**: Total quantity of the product sold as "internal" within the date range.
    - [ ] **Sale**: Total quantity of the product sold as non-internal within the date range.
    - [ ] **BF Stock (Beginning Forward Stock)**: The stock level at the beginning of the selected date range.
    - [ ] **Import**: The quantity of the product received into inventory within the date range.
- [ ] The report logic correctly calculates and displays the values for each column based on the selected date range.
- [ ] The PDF is formatted clearly for readability and printing.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Product Inventory Page -> Download PDF Button, Date Range Filter |
| User Flow | User navigates to Product Inventory -> Sets date range filter -> Clicks "Download PDF" -> System generates and downloads the report. |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Data Source | Report data is based on filtered inventory and order records. |
| BR2 | "Internal Order" Flag | The system must have a way to flag an order or order item as "Internal". |
| BR3 | Calculation Logic | All calculated fields (CN, Internal, Sale, BF Stock, Import) must be accurate. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Date Range | Date Range | Yes | | Start and End dates for the report. |
| Product ID | String | Yes | | Product identifier. |
| Product Code | String | Yes | | SKU. |
| Product Name | String | Yes | | |
| Price | Decimal | Yes | | |
| CN | Integer | Yes | | Calculated value. |
| Internal | Integer | Yes | | Calculated value. |
| Sale | Integer | Yes | | Calculated value. |
| BF Stock | Integer | Yes | | Calculated value. |
| Import | Integer | Yes | | Calculated value. |

---

## Dependencies

### Prerequisite Requirements
- FR-032 - Product Management - CRUD Operations.
- FR-037 - Sales Transaction Display.
- FR-039 - Stock Data Management - Display Current Stock.
- FR-040 - Stock Data Management - Display Stock Movement History.

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Row 26 defining the new PDF sales report. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- The system already captures whether an order is "Internal". If not, this functionality must be added to the order management FRs.
- "Import" refers to stock being added (e.g., from a purchase order), and the system has a way to track this.
- Calculating "BF Stock" requires querying the stock level at a specific point in the past, which can be computationally intensive and needs an efficient data model.

**Open Questions:**
- [ ] How is an "Internal Order" defined and marked in the system?
- [ ] How are "Import" and "CN" (returns/cancellations) events captured in the system?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
