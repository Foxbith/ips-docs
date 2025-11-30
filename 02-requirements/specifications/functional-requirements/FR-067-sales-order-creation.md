# FR-067: Sales Order Creation

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Functional

---

## Metadata

```yaml
id: FR-067
title: "Sales Order Creation"
category: "Functional"
subcategory: "Sales Management"
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

**As a** store staff or manager
**I want** to create sales orders for products
**So that** I can process customer purchases and manage inventory.

---

## Detailed Description

The system shall provide an interface for creating sales orders. This includes searching for products, adding them to an order, specifying quantities, and processing the sale. The system must also handle order cancellations by returning stock to inventory, and provide UI usability enhancements like using the Enter key for adding products.

---

## Acceptance Criteria

- [ ] Users can create a new sales order.
- [ ] Users can search for and add products to the order (using FR-035).
- [ ] Users can add a selected product to the order by pressing the Enter key, as an alternative to clicking an "Add" button.
- [ ] The system displays the price and calculates the total for each line item and the grand total.
- [ ] Upon completion, the system records the sales transaction (FR-037) and deducts the sold items from inventory (FR-039). The order status is set to "Paid".
- [ ] The system provides an option to mark an order or line item as "Internal".
- [ ] An authorized user can change the status of a "Paid" order to "Cancelled".
- [ ] Once an order is "Cancelled", it cannot be edited or reverted to "Paid".
- [ ] When an order status is changed to "Cancelled", the stock for all items in that order is automatically returned to the inventory. A confirmation modal is shown before finalizing the cancellation.

---

## UI/UX Considerations

| Aspect | Requirement |
|--------|-------------|
| Screen/Component | Sales Order Creation Page, Order List |
| User Flow | User searches for product -> Selects product -> Presses Enter or clicks Add -> Product is added to order -> User completes sale -> Order is created with "Paid" status. |
| Keyboard Shortcut | Pressing "Enter" after selecting a product in the search results should add it to the order. |

---

## Business Rules

| # | Rule | Description |
|---|------|-------------|
| BR1 | Stock Deduction | Stock is deducted from inventory only upon successful creation of a sales order. |
| BR2 | Stock Return on Cancellation | Stock is returned to inventory when an order's status is changed to "Cancelled". |
| BR3 | Status Immutability | A "Cancelled" order is final and cannot be modified. |

---

## Data Requirements

| Field | Type | Required | Validation | Notes |
|-------|------|----------|------------|-------|
| Order ID | String | Yes | Unique | Unique identifier for the order. |
| Order Items | List of Objects | Yes | | List of Product ID and Quantity. |
| Is Internal | Boolean | No | | Flag to mark the order as internal. |
| Order Status | String | Yes | "Paid", "Cancelled" | Status of the order. |
| Total Amount | Decimal | Yes | | Grand total of the order. |

---

## Dependencies

### Prerequisite Requirements
- FR-035 - Product Search and Filter.
- FR-037 - Sales Transaction Display.
- FR-039 - Stock Data Management - Display Current Stock.

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| UAT Feedback | 20250909_IPS_UAT 2 - Bug Report.csv | Rows 30 & 33 regarding Enter key and stock return on cancellation. |

---

## References

- **Planning Document:** `00-assets/documents/CC20240711001-สัญญาจ้างออกแบบและพัฒนาระบบอินทราเนตของโรงเรียนนานาชาติไพโอเนียร์.md`

---

## Notes

**Assumptions:**
- A user-friendly search interface is available for finding products to add to the order.

**Open Questions:**
- [ ] How are different payment methods (e.g., Cash, Bank Transfer as mentioned in other CRs) handled? This may require another FR.
- [ ] Is there a need for customer information to be attached to an order?

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | 2025-11-30 | Gemini | Initial requirement based on UAT feedback. | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
