# TC-001: IPS Test Suite Summary

> ISO/IEC 29110-5-1-2 Work Product: Test Cases

---

## Metadata

```yaml
id: TC-001
title: "IPS System Test Suite"
type: "UAT"
priority: "P1"
phase: 1
requirements: ["FR-001 to FR-010"]
version: "1.0"
status: "Active"
created: "2024-08-22"
last_modified: "2025-12-16"
author: "Foxbith QA Team"
automated: "No"
source_file: "Testcase [IPS].xlsx"
```

---

## 1. Test Suite Overview

### 1.1 Objective
Validate all functional requirements of the IPS (Pioneer International School Intranet System).

### 1.2 Test Coverage
This test suite covers 43 test modules across all system features.

---

## 2. Test Modules

### 2.1 Authentication
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Login | Login | High |

### 2.2 Student Management
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Student | Student | High |

### 2.3 Employee Management
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Employee Profile | Employee Profile | High |
| Employee Personal Information | Employee Personal Information | High |
| Employee Education | Employee Education | Medium |
| Employee Document | Employee Document | Medium |
| Employee Job Movements | Employee Job Movements | Medium |
| Employee Training | Employee Training | Medium |
| Training | Training | Medium |
| Employee Form Request | Employee Form Request | Medium |

### 2.4 Attendance & Leave
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Attendance | Attendance | High |
| Leave Request Admin | Leave Request_Admin | High |
| Leave Request User | Leave Request_User | High |

### 2.5 Academic Settings
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Academic Setting | Academic Setting | Medium |
| Time Setting | Time setting | Medium |
| Workload Setting | Workload setting | Medium |
| Education Classroom | Education Classroom | High |

### 2.6 Product Management
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Product Inventory | Product Inventory | High |
| Product Order | Product Order | High |
| Product List | Product List | High |
| Product Category | Product Category | Medium |

### 2.7 Stationary Management
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Stationary Inventory | Stationary Inventory | Medium |
| Stationary List | Stationary List | Medium |
| Stationary Category | Stationary Category | Low |
| Stationary Withdraw Admin | Stationary Withdraw_Admin | Medium |
| Stationary Withdraw User | Stationary Withdraw_User | Medium |

### 2.8 Dashboard
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Dashboard | Dashboard | High |

### 2.9 Form Requests
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Form Request Admin | Form Request_Admin | High |
| Form Request Employee | Form Request_Employee | High |
| Purchasing Form Admin | Purchasing Form_Admin | Medium |
| Purchasing Form Employee | Purchasing Form_Employee | Medium |
| Room Booking Admin | Room Booking Form_Admin | Medium |
| Room Booking Employee | Room Booking Form_Employee | Medium |
| CCTV Admin | CCTVForm_Admin | Medium |
| CCTV Employee | CCTV Form_Employee | Medium |

### 2.10 System Settings
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Permission Setting | Permission Setting | High |
| Company Profile | Company Profile | Medium |
| Leave Setting | Leave Setting | High |

### 2.11 Asset Management
| Module | Sheet Name | Priority |
|--------|------------|----------|
| Asset List | Asset List | High |
| Asset Model | Asset Model | Medium |
| Asset Type | Asset Type | Medium |
| Asset Location | Asset Location | Medium |

---

## 3. Sample Test Cases (Product List Module)

### TC-product_list_01: Access Product Menu
| Attribute | Value |
|-----------|-------|
| **Scenario** | Access "Product" menu from Sidebar |
| **Test Data** | order, inventory, products list, category |
| **Steps** | 1. Access Admin IPS website<br>2. Click Product menu |
| **Expected Result** | System displays Sidebar menu with: Order, Inventory, Products List, Category |
| **Priority** | High |

### TC-product_list_02: Access Products List
| Attribute | Value |
|-----------|-------|
| **Scenario** | Click "Products List" menu |
| **Test Data** | sidebar menu (product list) |
| **Steps** | 1. Access Admin IPS website<br>2. Click Product menu<br>3. Click Products List |
| **Expected Result** | System navigates to "Product" page |
| **Priority** | High |

### TC-product_list_03: View Product Page
| Attribute | Value |
|-----------|-------|
| **Scenario** | View Product page content |
| **Test Data** | create date, product, SKU, category, status |
| **Steps** | 1. Access Admin IPS<br>2. Click Product menu<br>3. Click Products List<br>4. View Product page |
| **Expected Result** | Page displays: Date filter, Filters (Product, SKU, Product ID, Category, Status), Upload/Download buttons, Data table with pagination |
| **Priority** | High |

### TC-product_list_04: Date Filter Test
| Attribute | Value |
|-----------|-------|
| **Scenario** | Test date filter functionality |
| **Test Data** | date |
| **Steps** | 1. Access Product List page<br>2. Test date filter |
| **Expected Result** | System filters data by selected date range |
| **Priority** | Medium |

### TC-product_list_05: Filter Test
| Attribute | Value |
|-----------|-------|
| **Scenario** | Test filter functionality |
| **Test Data** | product, product code (SKU), product id, category, status |
| **Steps** | 1. Access Product List page<br>2. Test filters |
| **Expected Result** | System filters data according to selected filters. Filters include: Product, Product Code (SKU), Product ID, Category, Status, Reset, Search buttons |
| **Priority** | Medium |

---

## 4. Execution History

### UAT 2 (2025-09-09 to 2025-09-22)
| Run # | Date | Tester | Environment | Result | Notes |
|-------|------|--------|-------------|--------|-------|
| 1 | 2025-09-09 | IPS Team | Staging | In Progress | UAT 2 execution |
| 2 | 2025-09-22 | IPS Team | Staging | Completed | UAT 2 completed |

---

## 5. Test Data Location

- **Test Case File:** `00-assets/2024-08-IPS 2/04 Software Testing/Testcase [IPS].xlsx`
- **UAT 2 Results:** `00-assets/2024-08-IPS 2/04 Software Testing/20250909_IPS_UAT 2.xlsx`
- **UAT 2 Evidence:** `00-assets/2024-08-IPS 2/04 Software Testing/09-09-2025-22-09-2025_UAT2/`

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-12-16 | - | Initial test suite based on Testcase [IPS].xlsx |

---

*Template follows ISO/IEC 29110-5-1-2 Test Cases requirements.*
