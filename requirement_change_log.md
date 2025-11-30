# Requirement Specification Change Log

This document logs the differences and clarifications identified between the initial functional requirements derived from the contract (`CC20240711001`) and the feedback from the UAT 2 Bug Report (`20250909_IPS_UAT 2 - Bug Report.csv`).

## 1. New Functional Requirements from UAT Feedback

The following new functional requirements were created to address Change Requests (CRs) from the UAT feedback that were not covered in the original contract's scope of work.

| FR ID | Title | UAT Feedback Reference | Summary of Requirement |
|---|---|---|---|
| **FR-065** | Room Booking Form | Rows 24, 25 | Defines a new, specific form for booking rooms with complex business rules, including a dropdown of rooms and logic to prevent overlapping bookings for specific rooms. |
| **FR-066** | Daily Internal Order Sales Report (PDF) | Row 26 | Defines a new daily PDF report for tracking "Internal Orders", including specific columns for stock reconciliation (BF Stock, Import, Sale, Internal, CN). |
| **FR-067** | Sales Order Creation | Rows 30, 33 | Formalizes the process for creating sales orders. Incorporates UAT feedback to allow using the "Enter" key to add products and to ensure stock is returned to inventory when an order is cancelled. |
| **FR-068** | Student Academic Enrollment Report | Rows 31, 38 | Defines a new report to show all academic programs a specific student is enrolled in. Based on feedback, this report must be exportable to PDF and include a "Receipt Date" column. |
| **FR-069** | Individual Record PDF Export | Row 41 | Defines a general feature to allow users to download a formatted PDF summary of a single data record (e.g., one form submission, one classroom record) from various modules. |

## 2. Modifications to Existing Functional Requirements

The following functional requirements were updated to clarify behavior or add specific rules based on UAT feedback.

| FR ID | Title | UAT Feedback Reference | Summary of Change |
|---|---|---|---|
| **FR-009** | Academic Year Management and Leave Reset | Rows 2, 3 | Clarified that an "Academic Year" can span across calendar years (e.g., Aug 2025 - Jun 2026). Updated to ensure the system correctly handles date selection for these periods. |
| **FR-005** | Organizational Structure and Job Position Management | Row 22 | Added a new business rule (`BR3`) to explicitly prevent a user from being assigned as their own approver in any approval hierarchy. |
| **FR-006** | Leave Request and Approval Workflow | Row 22 | Added a new business rule (`BR4`) to enforce the "No Self-Approval" rule defined in FR-005 during the leave approval process. |
| **FR-049** | Teaching Equipment Borrowing Request Management - CRUD | Row 21 | The requirement was modified to allow users to create borrowing/withdrawal requests for equipment even if the current stock level is zero. |
| **FR-051**| Teaching Equipment Borrowing Request Approval | Row 21 | The approval workflow was clarified to separate "Approval" from "Fulfillment". Stock is now only deducted at the fulfillment stage, and fulfillment is blocked if stock is insufficient. |
| **FR-018** | Student Profile Management - Display Comprehensive Information | Rows 34, 42 | Updated the data requirements to include specific fields for `Parent/Guardian Name` and `Parent/Guardian Phone`, rather than a generic "Family Information" object. |
| **FR-023** | Student Data Import and Export (Excel) | Rows 34, 42 | Updated to explicitly state that parent/guardian information must be included as part of the student data import and export templates and processes. |
| **FR-028** | Configurable Approval Forms | Rows 8, 35 | Added a note specifying that for the "Purchasing Form", the product name field should be a free-text input, not a selection from the product database, based on user feedback. |
| **FR-035** | Product Search and Filter | Row 9 | Added a business rule (`BR3`) to emphasize that product search results must be accurate and reflect real-time data, especially in the context of the Sales Order creation screen. |
| **FR-039** | Stock Data Management - Display Current Stock | Row 14 | Clarified the requirement to include a configurable "Minimum Stock" threshold per product, which drives a "Running Out" status when met. |

This log summarizes the evolution of the system requirements from the initial contract to the post-UAT feedback stage.
