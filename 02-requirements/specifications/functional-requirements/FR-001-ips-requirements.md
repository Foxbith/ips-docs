# FR-001: IPS System Functional Requirements

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification

---

## Metadata

```yaml
id: FR-001
title: "IPS System Requirements"
project: "IPS - Pioneer International School Intranet System"
phase: 1
version: "1.0"
status: "Approved"
created: "2024-08-06"
last_modified: "2025-12-16"
author: "Foxbith"
approved_by: "IPS"
source_file: "IPS-Data Inventory.xlsx"
```

---

## 1. Login System (FR-001-LOGIN)

### 1.1 User Acceptance Criteria
- Users can login via Google authentication (G Suite @ips.ac.th)

### 1.2 Technical Requirements
- **Database:** 1 month initial data
- **Authentication:** Google OAuth via G Suite

---

## 2. Employee Module (FR-002-EMPLOYEE)

### 2.1 Time Attendance System
| # | Feature | Description |
|---|---------|-------------|
| 1 | Time-Attendance | Support time attendance recording |
| 2 | Finger Scan Import | Import attendance data from Finger Scan system |
| 3 | Attendance Summary | Display and summarize attendance data per employee |
| 4 | Leave Summary | Display late arrivals, sick leave, vacation days per employee |
| 5 | Organization Chart | Support hierarchy structure based on approval authority |
| 6 | Job Description | Allow input and PDF upload for job descriptions |
| 7 | Leave Request | Support leave approval with hierarchical approval workflow |
| 8 | Email Notification | Notify supervisors via email for leave requests/approvals |
| 9 | Leave Rules | Configure leave policies (days per month, consecutive days) |
| 10 | Leave Settings | Set clock-in/out times, cut-off, holidays, special leaves, etc. |
| 11 | Leave Cycle | Support leave period configuration with reset by academic year |
| 12 | Present Form | Support off-site work conditions without leave deduction |
| 13 | Excel Export | Export employee data to Excel |

### 2.2 Employee Profile Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | General Info | Name, position, phone, email, address |
| 2 | Education Info | Education history |
| 3 | Work Experience | Work history and evaluations |
| 4 | Teaching Schedule | Homeroom, After School schedules |
| 5 | Training History | Course name, organization, date, budget |
| 6 | Probation Evaluation | Probation period results |

### 2.3 Employee Benefits & Welfare
| # | Feature | Description |
|---|---------|-------------|
| 1 | Benefits Tracking | Social security, teacher fund, group insurance |
| 2 | Document Storage | Personal documents: contracts, work permits, visas |
| 3 | CRUD Operations | Add/Edit/Delete employee data |
| 4 | Search & Filter | Search and filter employee records |
| 5 | Status Management | Active employee vs. resigned employee |
| 6 | Excel Export | Export employee data |

### 2.4 Additional Requirements
- **Due Date Alerts:** Notify employees when documents are expiring (e.g., work permits, visas)
- **Leave Cycle:** 1 year cycle from July 1 to June 30

---

## 3. Student Module (FR-003-STUDENT)

### 3.1 Student Information Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | General Info | Name, student ID, class, address |
| 2 | Family Info | Parent/guardian information |
| 3 | Contact Info | Phone, email |
| 4 | Delete Records | Remove student data |
| 5 | Class Settings | Configure grade levels and classes |
| 6 | Search & Filter | Search and filter students |
| 7 | Status Management | Current student vs. alumni |
| 8 | Import/Export | Excel import and export |

### 3.2 Integration
- **Schoolbase Integration:** Email data integration
- **After School Connection:** Connect student data for After School programs

---

## 4. Asset Module (FR-004-ASSET)

### 4.1 Asset Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Asset Configuration | Type, code, brand, model, vendor, location |
| 2 | Asset Details | Serial number, status, size, weight, color, OS, specs |
| 3 | Status Management | Working, damaged, broken |
| 4 | CRUD Operations | Add/Edit/Delete assets |
| 5 | Excel Export | Export asset data |

### 4.2 Additional Requirements
- **Cost Tracking:** Store asset costs for annual accounting reports

---

## 5. Form Module (FR-005-FORM)

### 5.1 Form Types
| Form Type | Description | Approvers |
|-----------|-------------|-----------|
| Present Form | Off-site work form (name, time not scanned, approver) | AP, Principal |
| CCTV Form | CCTV access request (name, approver) | AP, Principal |
| Leave Form | Absence, late, leave requests | AP, Principal |
| Stationary Form | Stationary request | AP, Principal |
| Booking Form | Meeting room booking | AP, Principal |

### 5.2 Form Features
| # | Feature | Description |
|---|---------|-------------|
| 1 | Form Configuration | Configure up to 5 form types |
| 2 | Form List | Display pending forms with type, details, approver, requester |
| 3 | CRUD Operations | Create/Edit/Delete forms |
| 4 | File Upload | Support file and image uploads |
| 5 | Status Management | Pending, Approved, Rejected |
| 6 | Search & Filter | Search and filter forms |

---

## 6. Product Module (FR-006-PRODUCT)

### 6.1 Product Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Product Types | Books, stationery, supplies, personal items, souvenirs |
| 2 | Barcode/QR | Generate Barcode and QR codes for products |
| 3 | Product Details | Code, name, description, price, image, inventory |
| 4 | CRUD Operations | Add/Edit/Delete products |
| 5 | Search | Search by name, code, category, brand, vendor |
| 6 | CSV Import | Import products via CSV file |

### 6.2 Sales Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Sales List | Display sales records (product, price, quantity) |
| 2 | CRUD Operations | Add/Edit/Delete sales |
| 3 | Invoice | Generate sales invoices |
| 4 | Excel Export | Export sales data |

### 6.3 Inventory Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Stock Display | Show remaining inventory |
| 2 | Stock History | Display stock adjustment history |
| 3 | Status Management | Expired, Active |
| 4 | Excel Export | Export inventory data |

### 6.4 Additional Requirements
- **Cost Tracking:** Store product costs for accounting
- **Draft Status:** Products start as draft until approved

---

## 7. Stationary Module (FR-007-STATIONARY)

### 7.1 Stationary Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Configuration | Type, code, brand, model, vendor, location |
| 2 | General Info | Name, type, code, brand, model, size, weight, color, vendor, image |
| 3 | CRUD Operations | Add/Edit/Delete items |
| 4 | Status Management | Working, damaged, broken |
| 5 | Search & Filter | Search and filter items |
| 6 | Excel Export | Export stationary data |

### 7.2 Withdrawal Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Withdrawal Info | Date, requester, items, status |
| 2 | CRUD Operations | Add/Edit/Delete withdrawals |
| 3 | Search & Filter | Search and filter withdrawals |
| 4 | Approval | Approve individual items or bulk approve |
| 5 | Notification | In-system withdrawal notifications |
| 6 | Excel Export | Export withdrawal data |

### 7.3 Additional Requirements
- **Cost Tracking:** Store costs for accounting reports

---

## 8. Academic Module (FR-008-ACADEMIC)

### 8.1 Classroom Management
| # | Feature | Description |
|---|---------|-------------|
| 1 | Class Settings | Configure classrooms and subjects (sports, music, art, language) |
| 2 | Class Booking | Book After School, Intervention, ESP classes |
| 3 | Program Info | Program name, description, image, instructor, schedule, fees |
| 4 | Search | Search by name, description, instructor, class, subject group |
| 5 | Excel Export | Export booking data |

### 8.2 Required Information
- Class name
- Schedule
- Instructor
- Students
- Payment form (sample from IPS required)

---

## 9. Dashboard Module (FR-009-DASHBOARD)

### 9.1 Dashboard Features
| # | Feature | Description |
|---|---------|-------------|
| 1 | Leave Summary | Display leave reports from Employee module |
| 2 | Role-based Views | Different report views based on user permissions |

---

## 10. Settings Module (FR-010-SETTINGS)

### 10.1 System Settings
| # | Feature | Description |
|---|---------|-------------|
| 1 | Multi-branch | Support 2 branches with separate databases |
| 2 | Single Language | Support 1 language |
| 3 | Access Control | Configure data access permissions (hide/show menus, view/edit/delete) |
| 4 | Group Permissions | Configure permissions by group (HR, Management, etc.) |
| 5 | User Management | Create/Edit/Delete user accounts linked to employee profiles |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-12-16 | - | Initial requirements based on IPS-Data Inventory.xlsx |

---

*Document follows ISO/IEC 29110-5-1-2 Requirements Specification requirements.*
