# Requirements Traceability Matrix

> ISO/IEC 29110-5-1-2 Work Product: Traceability Record

---

## Metadata

```yaml
project: "IPS - Pioneer International School Intranet System"
version: "1.0"
last_updated: "2025-12-16"
maintained_by: "Danupha Mangnoi"
document_ref: "IPS-Traceability Record.xlsx"
```

---

## Purpose

This matrix traces requirements through design, implementation, and testing to ensure complete coverage and facilitate impact analysis for changes.

---

## 1. Requirements to Design Traceability

### 1.1 Functional Requirements

| Req ID | Requirement Title | Design Component | Design Document | Status |
|--------|-------------------|------------------|-----------------|--------|
| FR-001 | Login (LogIn) | Authentication Module | UX/UI Design | Designed |
| FR-002 | Employee Module | Employee Management | UX/UI Design | Designed |
| FR-003 | Student Module | Student Management | UX/UI Design | Designed |
| FR-004 | Asset Module | Asset Management | UX/UI Design | Designed |
| FR-005 | Form Module | Form Request System | UX/UI Design | Designed |
| FR-006 | Product Module | Product Management | UX/UI Design | Designed |
| FR-007 | Stationary Module | Stationary Management | UX/UI Design | Designed |
| FR-008 | Academic Module | Classroom Management | UX/UI Design | Designed |
| FR-009 | Dashboard | Reporting & Analytics | UX/UI Design | Designed |
| FR-010 | Settings | System Configuration | UX/UI Design | Designed |

### 1.2 Sub-Feature Requirements

| Req ID | Parent | Sub-Feature | Status |
|--------|--------|-------------|--------|
| FR-002-01 | FR-002 | Time Attendance | Designed |
| FR-002-02 | FR-002 | Leave Request | Designed |
| FR-002-03 | FR-002 | Employee Profile | Designed |
| FR-002-04 | FR-002 | Employee Training | Designed |
| FR-005-01 | FR-005 | Present Form | Designed |
| FR-005-02 | FR-005 | CCTV Form | Designed |
| FR-005-03 | FR-005 | Leave Form | Designed |
| FR-005-04 | FR-005 | Stationary Form | Designed |
| FR-005-05 | FR-005 | Booking Form | Designed |
| FR-006-01 | FR-006 | Product List | Designed |
| FR-006-02 | FR-006 | Product Orders | Designed |
| FR-006-03 | FR-006 | Product Inventory | Designed |

---

## 2. Requirements to Test Cases Traceability

| Req ID | Requirement Title | Test Case(s) | Test Type | Coverage |
|--------|-------------------|--------------|-----------|----------|
| FR-001 | Login | TC-Login-* | UAT | Complete |
| FR-002 | Employee Module | TC-Employee-*, TC-Leave-*, TC-Attendance-* | UAT | Complete |
| FR-003 | Student Module | TC-Student-* | UAT | Complete |
| FR-004 | Asset Module | TC-Asset-* | UAT | Complete |
| FR-005 | Form Module | TC-Form-*, TC-CCTV-*, TC-Booking-* | UAT | Complete |
| FR-006 | Product Module | TC-Product-*, TC-ProductList-* | UAT | Complete |
| FR-007 | Stationary Module | TC-Stationary-* | UAT | Complete |
| FR-008 | Academic Module | TC-Academic-*, TC-Classroom-* | UAT | Complete |
| FR-009 | Dashboard | TC-Dashboard-* | UAT | Complete |
| FR-010 | Settings | TC-Permission-*, TC-Company-* | UAT | Complete |

---

## 3. Test Coverage by Module

| Module | Test Cases | Test Sheets |
|--------|------------|-------------|
| Login | login_* | Login |
| Student | student_* | Student |
| Employee Profile | employee_profile_* | Employee Profile |
| Employee Personal Info | employee_personal_* | Employee Personal Information |
| Employee Education | employee_education_* | Employee Education |
| Employee Document | employee_document_* | Employee Document |
| Employee Job Movements | employee_job_* | Employee Job Movements |
| Employee Training | employee_training_* | Employee Training |
| Training | training_* | Training |
| Employee Form Request | employee_form_* | Employee Form Request |
| Academic Setting | academic_setting_* | Academic Setting |
| Time Setting | time_setting_* | Time setting |
| Workload Setting | workload_setting_* | Workload setting |
| Attendance | attendance_* | Attendance |
| Leave Request Admin | leave_admin_* | Leave Request_Admin |
| Leave Request User | leave_user_* | Leave Request_User |
| Product Inventory | product_inventory_* | Product Inventory |
| Product Order | product_order_* | Product Order |
| Product List | product_list_* | Product List |
| Product Category | product_category_* | Product Category |
| Stationary Inventory | stationary_inventory_* | Stationary Inventory |
| Stationary List | stationary_list_* | Stationary List |
| Stationary Category | stationary_category_* | Stationary Category |
| Stationary Withdraw Admin | stationary_withdraw_admin_* | Stationary Withdraw_Admin |
| Stationary Withdraw User | stationary_withdraw_user_* | Stationary Withdraw_User |
| Dashboard | dashboard_* | Dashboard |
| Form Request Admin | form_request_admin_* | Form Request_Admin |
| Form Request Employee | form_request_employee_* | Form Request_Employee |
| Purchasing Form Admin | purchasing_admin_* | Purchasing Form_Admin |
| Purchasing Form Employee | purchasing_employee_* | Purchasing Form_Employee |
| Room Booking Admin | room_booking_admin_* | Room Booking Form_Admin |
| Room Booking Employee | room_booking_employee_* | Room Booking Form_Employee |
| CCTV Admin | cctv_admin_* | CCTVForm_Admin |
| CCTV Employee | cctv_employee_* | CCTV Form_Employee |
| Permission Setting | permission_* | Permission Setting |
| Company Profile | company_* | Company Profile |
| Leave Setting | leave_setting_* | Leave Setting |
| Asset List | asset_list_* | Asset List |
| Asset Model | asset_model_* | Asset Model |
| Asset Type | asset_type_* | Asset Type |
| Asset Location | asset_location_* | Asset Location |
| Education Classroom | education_classroom_* | Education Classroom |

---

## 4. Coverage Summary

### By Category
| Category | Total | Designed | Implemented | Tested | Coverage % |
|----------|-------|----------|-------------|--------|------------|
| Login | 1 | 1 | 1 | 1 | 100% |
| Employee | 10 | 10 | In Progress | Partial | 80% |
| Student | 1 | 1 | In Progress | Partial | 80% |
| Asset | 4 | 4 | In Progress | Partial | 80% |
| Form | 5 | 5 | In Progress | Partial | 80% |
| Product | 4 | 4 | In Progress | Partial | 80% |
| Stationary | 5 | 5 | In Progress | Partial | 80% |
| Academic | 1 | 1 | In Progress | Partial | 80% |
| Dashboard | 1 | 1 | In Progress | Partial | 80% |
| Settings | 3 | 3 | In Progress | Partial | 80% |
| **Total** | **35** | **35** | **In Progress** | **Partial** | **80%** |

---

## 5. UAT Tracking

### UAT 2 Results (2025-09-09 to 2025-09-22)
- Test Case Reference: `20250909_IPS_UAT 2.xlsx`
- Evidence Location: `00-assets/2024-08-IPS 2/04 Software Testing/09-09-2025-22-09-2025_UAT2/`

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-12-16 | Claude | Initial matrix based on IPS-Traceability Record.xlsx |

---

*Matrix follows ISO/IEC 29110-5-1-2 Traceability Record requirements.*
