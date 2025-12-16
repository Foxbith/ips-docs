# TC-002: IPS Detailed Test Cases

> ISO/IEC 29110-5-1-2 Work Product: Test Cases and Test Procedures

---

## Metadata

```yaml
id: TC-002
title: "IPS Detailed Test Cases"
type: "UAT"
project: "IPS - Pioneer International School Intranet System"
version: "1.0"
status: "Active"
created: "2025-12-16"
author: "Foxbith QA Team"
```

---

## 1. Login Module

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-LOGIN-001 | Login | Verify Google OAuth login | User has valid @ips.ac.th account | 1. Navigate to login page<br>2. Click "Login with Google"<br>3. Enter valid @ips.ac.th credentials | User successfully logged in and redirected to dashboard | High |
| Web | TC-LOGIN-002 | Login | Verify invalid domain login rejected | User has non-IPS Google account | 1. Navigate to login page<br>2. Click "Login with Google"<br>3. Enter non @ips.ac.th account | System displays error message and denies access | High |
| Web | TC-LOGIN-003 | Login | Verify logout functionality | User is logged in | 1. Click user profile<br>2. Click "Logout" | User logged out and redirected to login page | High |
| Web | TC-LOGIN-004 | Login | Verify session persistence | User is logged in | 1. Login successfully<br>2. Close browser<br>3. Reopen and navigate to site | Session maintained or requires re-login based on settings | Medium |

---

## 2. Employee Module

### 2.1 Employee Profile

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-EMP-001 | Employee Profile | View employee list | User logged in with HR permission | 1. Click Employee menu<br>2. View employee list | System displays all employees with Name, Position, Department, Status | High |
| Web | TC-EMP-002 | Employee Profile | Search employee by name | Employee list is displayed | 1. Enter employee name in search<br>2. Click Search | System filters and displays matching employees | High |
| Web | TC-EMP-003 | Employee Profile | Filter employee by status | Employee list is displayed | 1. Select status filter (Active/Resigned)<br>2. Click Search | System displays employees matching selected status | Medium |
| Web | TC-EMP-004 | Employee Profile | View employee details | Employee list is displayed | 1. Click on employee row<br>2. View details page | System displays employee details: personal info, education, documents | High |
| Web | TC-EMP-005 | Employee Profile | Add new employee | User has HR permission | 1. Click "Add Employee"<br>2. Fill required fields<br>3. Click Save | New employee created and displayed in list | High |
| Web | TC-EMP-006 | Employee Profile | Edit employee information | Employee exists | 1. Open employee details<br>2. Click Edit<br>3. Modify fields<br>4. Save | Employee information updated successfully | High |
| Web | TC-EMP-007 | Employee Profile | Delete employee | Employee exists | 1. Select employee<br>2. Click Delete<br>3. Confirm deletion | Employee removed from system | Medium |
| Web | TC-EMP-008 | Employee Profile | Export employee list to Excel | Employees exist | 1. Click Export<br>2. Select Excel format | Excel file downloaded with employee data | Medium |

### 2.2 Employee Personal Information

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-EMP-PI-001 | Personal Info | View personal information tab | Employee detail page open | 1. Click Personal Information tab | System displays: Name, Address, Phone, Email, ID Card | High |
| Web | TC-EMP-PI-002 | Personal Info | Edit personal information | Employee detail page open | 1. Click Edit<br>2. Modify personal fields<br>3. Save | Personal information updated | High |
| Web | TC-EMP-PI-003 | Personal Info | Validate required fields | Edit mode active | 1. Clear required fields<br>2. Click Save | System shows validation errors for required fields | Medium |

### 2.3 Employee Education

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-EMP-ED-001 | Education | View education history | Employee detail page open | 1. Click Education tab | System displays education records: Degree, Institution, Year | Medium |
| Web | TC-EMP-ED-002 | Education | Add education record | Education tab open | 1. Click Add Education<br>2. Fill degree, institution, year<br>3. Save | Education record added to employee | Medium |
| Web | TC-EMP-ED-003 | Education | Edit education record | Education record exists | 1. Click Edit on record<br>2. Modify fields<br>3. Save | Education record updated | Medium |
| Web | TC-EMP-ED-004 | Education | Delete education record | Education record exists | 1. Click Delete<br>2. Confirm | Education record removed | Low |

### 2.4 Employee Documents

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-EMP-DOC-001 | Documents | View employee documents | Employee detail page open | 1. Click Documents tab | System displays uploaded documents list | Medium |
| Web | TC-EMP-DOC-002 | Documents | Upload document | Documents tab open | 1. Click Upload<br>2. Select file (PDF/Image)<br>3. Add description<br>4. Save | Document uploaded and displayed in list | High |
| Web | TC-EMP-DOC-003 | Documents | Download document | Document exists | 1. Click Download on document | Document downloaded to local machine | Medium |
| Web | TC-EMP-DOC-004 | Documents | Delete document | Document exists | 1. Click Delete<br>2. Confirm | Document removed from employee record | Medium |
| Web | TC-EMP-DOC-005 | Documents | Document expiry alert | Document has expiry date | 1. Set document with expiry date<br>2. Wait for alert period | System sends notification before document expires | High |

### 2.5 Employee Training

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-EMP-TR-001 | Training | View training history | Employee detail page open | 1. Click Training tab | System displays training records: Course, Date, Organization, Budget | Medium |
| Web | TC-EMP-TR-002 | Training | Add training record | Training tab open | 1. Click Add Training<br>2. Fill course details<br>3. Save | Training record added | Medium |
| Web | TC-EMP-TR-003 | Training | Edit training record | Training record exists | 1. Click Edit<br>2. Modify fields<br>3. Save | Training record updated | Medium |

---

## 3. Attendance Module

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-ATT-001 | Attendance | View attendance list | User logged in | 1. Click Attendance menu | System displays attendance records with Date, Employee, Clock In, Clock Out | High |
| Web | TC-ATT-002 | Attendance | Filter by date range | Attendance page open | 1. Select start date<br>2. Select end date<br>3. Click Search | System filters attendance by date range | High |
| Web | TC-ATT-003 | Attendance | Filter by employee | Attendance page open | 1. Select employee from dropdown<br>2. Click Search | System displays attendance for selected employee | High |
| Web | TC-ATT-004 | Attendance | Import from Finger Scan | Admin permission | 1. Click Import<br>2. Upload Finger Scan file<br>3. Confirm import | Attendance data imported from file | High |
| Web | TC-ATT-005 | Attendance | Export attendance report | Attendance data exists | 1. Click Export<br>2. Select format | Attendance report exported | Medium |
| Web | TC-ATT-006 | Attendance | View late arrivals summary | Attendance data exists | 1. View attendance summary | System shows count of late arrivals | Medium |

---

## 4. Leave Request Module

### 4.1 Leave Request - Admin

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-LEAVE-ADM-001 | Leave Admin | View all leave requests | Admin logged in | 1. Click Leave Request menu | System displays all leave requests with Employee, Type, Dates, Status | High |
| Web | TC-LEAVE-ADM-002 | Leave Admin | Filter by leave type | Leave list displayed | 1. Select leave type<br>2. Click Search | System filters by selected leave type | Medium |
| Web | TC-LEAVE-ADM-003 | Leave Admin | Filter by status | Leave list displayed | 1. Select status (Pending/Approved/Rejected)<br>2. Search | System filters by status | Medium |
| Web | TC-LEAVE-ADM-004 | Leave Admin | Approve leave request | Pending request exists | 1. Open leave request<br>2. Click Approve<br>3. Add comments (optional)<br>4. Confirm | Leave request approved, email sent to employee | High |
| Web | TC-LEAVE-ADM-005 | Leave Admin | Reject leave request | Pending request exists | 1. Open leave request<br>2. Click Reject<br>3. Add reason<br>4. Confirm | Leave request rejected, email sent to employee | High |
| Web | TC-LEAVE-ADM-006 | Leave Admin | View leave balance | Employee selected | 1. View employee leave details | System shows remaining leave days by type | High |

### 4.2 Leave Request - User

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-LEAVE-USR-001 | Leave User | View my leave requests | User logged in | 1. Click My Leave menu | System displays user's leave requests | High |
| Web | TC-LEAVE-USR-002 | Leave User | Submit leave request | User logged in | 1. Click New Leave Request<br>2. Select leave type<br>3. Select dates<br>4. Add reason<br>5. Submit | Leave request submitted, notification sent to approver | High |
| Web | TC-LEAVE-USR-003 | Leave User | Cancel pending request | Pending request exists | 1. Open pending request<br>2. Click Cancel<br>3. Confirm | Leave request cancelled | Medium |
| Web | TC-LEAVE-USR-004 | Leave User | View leave balance | User logged in | 1. View leave summary | System shows remaining leave days | High |
| Web | TC-LEAVE-USR-005 | Leave User | Attach documents to leave | Creating leave request | 1. Create leave request<br>2. Upload supporting document<br>3. Submit | Leave submitted with attachment | Medium |

---

## 5. Student Module

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-STU-001 | Student | View student list | User logged in with permission | 1. Click Student menu | System displays student list with ID, Name, Class, Status | High |
| Web | TC-STU-002 | Student | Search student | Student list displayed | 1. Enter student name/ID<br>2. Click Search | System displays matching students | High |
| Web | TC-STU-003 | Student | Filter by class | Student list displayed | 1. Select class from dropdown<br>2. Search | System filters students by class | High |
| Web | TC-STU-004 | Student | Filter by status | Student list displayed | 1. Select status (Current/Alumni)<br>2. Search | System filters by status | Medium |
| Web | TC-STU-005 | Student | View student details | Student list displayed | 1. Click on student row | System displays student details: Personal info, Family, Contact | High |
| Web | TC-STU-006 | Student | Add new student | User has permission | 1. Click Add Student<br>2. Fill required fields<br>3. Save | Student added to system | High |
| Web | TC-STU-007 | Student | Edit student | Student exists | 1. Open student details<br>2. Click Edit<br>3. Modify<br>4. Save | Student information updated | High |
| Web | TC-STU-008 | Student | Delete student | Student exists | 1. Select student<br>2. Click Delete<br>3. Confirm | Student removed from system | Medium |
| Web | TC-STU-009 | Student | Import students from Excel | User has permission | 1. Click Import<br>2. Upload Excel file<br>3. Confirm | Students imported from file | High |
| Web | TC-STU-010 | Student | Export students to Excel | Students exist | 1. Click Export | Excel file downloaded with student data | Medium |

---

## 6. Asset Module

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-AST-001 | Asset List | View asset list | User logged in | 1. Click Asset menu<br>2. Click Asset List | System displays assets with Code, Name, Type, Location, Status | High |
| Web | TC-AST-002 | Asset List | Search asset | Asset list displayed | 1. Enter asset name/code<br>2. Search | System displays matching assets | High |
| Web | TC-AST-003 | Asset List | Filter by type | Asset list displayed | 1. Select asset type<br>2. Search | System filters by type | Medium |
| Web | TC-AST-004 | Asset List | Filter by status | Asset list displayed | 1. Select status (Working/Damaged/Broken)<br>2. Search | System filters by status | Medium |
| Web | TC-AST-005 | Asset List | Filter by location | Asset list displayed | 1. Select location<br>2. Search | System filters by location | Medium |
| Web | TC-AST-006 | Asset List | Add new asset | User has permission | 1. Click Add Asset<br>2. Fill: Code, Name, Type, Serial, Location, Status, Cost<br>3. Save | Asset added to system | High |
| Web | TC-AST-007 | Asset List | Edit asset | Asset exists | 1. Open asset details<br>2. Edit fields<br>3. Save | Asset updated | High |
| Web | TC-AST-008 | Asset List | Delete asset | Asset exists | 1. Select asset<br>2. Delete<br>3. Confirm | Asset removed | Medium |
| Web | TC-AST-009 | Asset List | Upload asset image | Editing asset | 1. Click Upload Image<br>2. Select image<br>3. Save | Image attached to asset | Low |
| Web | TC-AST-010 | Asset List | Export asset report | Assets exist | 1. Click Export | Asset report downloaded | Medium |
| Web | TC-AST-011 | Asset Model | Manage asset models | Asset Model page open | 1. Add/Edit/Delete asset models | Asset models managed successfully | Medium |
| Web | TC-AST-012 | Asset Type | Manage asset types | Asset Type page open | 1. Add/Edit/Delete asset types | Asset types managed successfully | Medium |
| Web | TC-AST-013 | Asset Location | Manage asset locations | Asset Location page open | 1. Add/Edit/Delete locations | Locations managed successfully | Medium |

---

## 7. Product Module

### 7.1 Product List

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-PROD-001 | Product List | Access Product menu | User logged in | 1. Click Product from sidebar | System displays submenu: Order, Inventory, Products List, Category | High |
| Web | TC-PROD-002 | Product List | View product list | Products List selected | 1. Click Products List | System displays products with Date, Name, SKU, Category, Status | High |
| Web | TC-PROD-003 | Product List | Search by SKU | Product list displayed | 1. Enter SKU<br>2. Search | System displays matching product | High |
| Web | TC-PROD-004 | Product List | Filter by date | Product list displayed | 1. Select date range<br>2. Apply | System filters by date | Medium |
| Web | TC-PROD-005 | Product List | Filter by category | Product list displayed | 1. Select category<br>2. Search | System filters by category | Medium |
| Web | TC-PROD-006 | Product List | Filter by status | Product list displayed | 1. Select status<br>2. Search | System filters by status | Medium |
| Web | TC-PROD-007 | Product List | Add new product | User has permission | 1. Click Add Product<br>2. Fill: Name, SKU, Category, Price, Description<br>3. Save | Product added with Draft status | High |
| Web | TC-PROD-008 | Product List | Edit product | Product exists | 1. Open product<br>2. Edit fields<br>3. Save | Product updated | High |
| Web | TC-PROD-009 | Product List | Delete product | Product exists | 1. Select product<br>2. Delete<br>3. Confirm | Product removed | Medium |
| Web | TC-PROD-010 | Product List | Upload product image | Editing product | 1. Click Upload<br>2. Select image<br>3. Save | Image attached to product | Medium |
| Web | TC-PROD-011 | Product List | Import products via CSV | User has permission | 1. Click Upload<br>2. Select CSV<br>3. Upload file | Products imported from CSV | High |
| Web | TC-PROD-012 | Product List | Download CSV template | Upload modal open | 1. Click Download Template | CSV template downloaded | Medium |
| Web | TC-PROD-013 | Product List | Export products | Products exist | 1. Click Download/Export | Product data exported | Medium |
| Web | TC-PROD-014 | Product List | Change page size | Product list displayed | 1. Select rows per page (10/20/50) | List displays selected number of rows | Low |
| Web | TC-PROD-015 | Product List | Navigate pagination | Multiple pages exist | 1. Click Next/Previous page | System navigates to correct page | Low |
| Web | TC-PROD-016 | Product List | Generate barcode | Product exists | 1. View product details | Barcode displayed for product | Medium |
| Web | TC-PROD-017 | Product List | Generate QR code | Product exists | 1. View product details | QR code displayed for product | Medium |

### 7.2 Product Order

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-ORD-001 | Product Order | View order list | Orders exist | 1. Click Order menu | System displays orders with Date, Customer, Items, Total, Status | High |
| Web | TC-ORD-002 | Product Order | Create new order | Products exist | 1. Click New Order<br>2. Add products<br>3. Set quantities<br>4. Submit | Order created | High |
| Web | TC-ORD-003 | Product Order | Edit order | Order exists | 1. Open order<br>2. Modify items/quantities<br>3. Save | Order updated | High |
| Web | TC-ORD-004 | Product Order | Cancel order | Order exists | 1. Open order<br>2. Click Cancel<br>3. Confirm | Order cancelled | Medium |
| Web | TC-ORD-005 | Product Order | Generate invoice | Order completed | 1. Open order<br>2. Click Print Invoice | Invoice generated with order details | High |
| Web | TC-ORD-006 | Product Order | Export orders | Orders exist | 1. Click Export | Order data exported to Excel | Medium |

### 7.3 Product Inventory

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-INV-001 | Inventory | View inventory | Products exist | 1. Click Inventory menu | System displays stock levels for all products | High |
| Web | TC-INV-002 | Inventory | View stock history | Product selected | 1. Click on product | System shows stock adjustment history | Medium |
| Web | TC-INV-003 | Inventory | Adjust stock | User has permission | 1. Select product<br>2. Click Adjust Stock<br>3. Enter adjustment<br>4. Save | Stock level updated, history recorded | High |
| Web | TC-INV-004 | Inventory | Low stock alert | Stock below threshold | 1. Set minimum stock level<br>2. Stock falls below | System shows low stock warning | Medium |
| Web | TC-INV-005 | Inventory | Export inventory | Inventory data exists | 1. Click Export | Inventory report exported | Medium |

### 7.4 Product Category

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-CAT-001 | Category | View categories | Categories exist | 1. Click Category menu | System displays category list | Medium |
| Web | TC-CAT-002 | Category | Add category | User has permission | 1. Click Add<br>2. Enter name<br>3. Save | Category created | Medium |
| Web | TC-CAT-003 | Category | Edit category | Category exists | 1. Click Edit<br>2. Modify name<br>3. Save | Category updated | Medium |
| Web | TC-CAT-004 | Category | Delete category | Category exists, no products | 1. Click Delete<br>2. Confirm | Category deleted | Low |

---

## 8. Stationary Module

### 8.1 Stationary List

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-STAT-001 | Stationary List | View stationary list | User logged in | 1. Click Stationary menu<br>2. Click List | System displays stationary items | Medium |
| Web | TC-STAT-002 | Stationary List | Add stationary item | User has permission | 1. Click Add<br>2. Fill: Name, Code, Type, Quantity<br>3. Save | Item added | Medium |
| Web | TC-STAT-003 | Stationary List | Edit stationary | Item exists | 1. Edit item<br>2. Save | Item updated | Medium |
| Web | TC-STAT-004 | Stationary List | Delete stationary | Item exists | 1. Delete item<br>2. Confirm | Item removed | Low |

### 8.2 Stationary Withdraw - Admin

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-STAT-WD-ADM-001 | Withdraw Admin | View withdrawal requests | Requests exist | 1. Click Withdraw menu | System displays withdrawal requests | Medium |
| Web | TC-STAT-WD-ADM-002 | Withdraw Admin | Approve withdrawal | Pending request exists | 1. Open request<br>2. Click Approve | Request approved, stock deducted | Medium |
| Web | TC-STAT-WD-ADM-003 | Withdraw Admin | Reject withdrawal | Pending request exists | 1. Open request<br>2. Click Reject<br>3. Add reason | Request rejected | Medium |
| Web | TC-STAT-WD-ADM-004 | Withdraw Admin | Bulk approve | Multiple pending requests | 1. Select requests<br>2. Click Approve All | All selected requests approved | Medium |

### 8.3 Stationary Withdraw - User

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-STAT-WD-USR-001 | Withdraw User | Submit withdrawal request | User logged in | 1. Click New Request<br>2. Select items<br>3. Enter quantities<br>4. Submit | Request submitted to approver | Medium |
| Web | TC-STAT-WD-USR-002 | Withdraw User | View my requests | User logged in | 1. View my withdrawals | System displays user's requests with status | Medium |
| Web | TC-STAT-WD-USR-003 | Withdraw User | Cancel request | Pending request exists | 1. Click Cancel<br>2. Confirm | Request cancelled | Low |

---

## 9. Form Request Module

### 9.1 Form Request - Admin

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-FORM-ADM-001 | Form Admin | View all form requests | Admin logged in | 1. Click Form Request menu | System displays all form requests | High |
| Web | TC-FORM-ADM-002 | Form Admin | Filter by form type | Form list displayed | 1. Select form type<br>2. Search | System filters by type | Medium |
| Web | TC-FORM-ADM-003 | Form Admin | Approve form request | Pending form exists | 1. Open form<br>2. Click Approve | Form approved, requester notified | High |
| Web | TC-FORM-ADM-004 | Form Admin | Reject form request | Pending form exists | 1. Open form<br>2. Click Reject<br>3. Add reason | Form rejected, requester notified | High |

### 9.2 Form Request - Employee

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-FORM-EMP-001 | Form Employee | Submit Present Form | User logged in | 1. Click New Form<br>2. Select Present Form<br>3. Fill: Date, Time, Reason<br>4. Submit | Present form submitted | High |
| Web | TC-FORM-EMP-002 | Form Employee | Submit CCTV Form | User logged in | 1. Click New Form<br>2. Select CCTV Form<br>3. Fill details<br>4. Submit | CCTV form submitted | Medium |
| Web | TC-FORM-EMP-003 | Form Employee | Submit Booking Form | User logged in | 1. Click New Form<br>2. Select Room Booking<br>3. Select room, date, time<br>4. Submit | Booking form submitted | Medium |
| Web | TC-FORM-EMP-004 | Form Employee | Submit Purchasing Form | User logged in | 1. Click New Form<br>2. Select Purchasing<br>3. Add items<br>4. Submit | Purchasing form submitted | Medium |
| Web | TC-FORM-EMP-005 | Form Employee | Upload attachment | Creating form | 1. Create form<br>2. Click Upload<br>3. Select file<br>4. Submit | Form submitted with attachment | Medium |
| Web | TC-FORM-EMP-006 | Form Employee | View my forms | User logged in | 1. Click My Forms | System displays user's form requests | High |

---

## 10. Academic Module

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-ACAD-001 | Classroom | View classroom list | User logged in | 1. Click Academic menu<br>2. Click Classroom | System displays classrooms | High |
| Web | TC-ACAD-002 | Classroom | Add new classroom | User has permission | 1. Click Add<br>2. Fill: Name, Subject, Instructor, Schedule, Fee<br>3. Save | Classroom created | High |
| Web | TC-ACAD-003 | Classroom | Edit classroom | Classroom exists | 1. Open classroom<br>2. Edit details<br>3. Save | Classroom updated | High |
| Web | TC-ACAD-004 | Classroom | Delete classroom | Classroom exists | 1. Delete classroom<br>2. Confirm | Classroom removed | Medium |
| Web | TC-ACAD-005 | Classroom | Enroll student | Classroom exists | 1. Open classroom<br>2. Click Add Student<br>3. Select student<br>4. Save | Student enrolled in classroom | High |
| Web | TC-ACAD-006 | Classroom | Remove student | Student enrolled | 1. Open classroom<br>2. Select student<br>3. Click Remove | Student removed from classroom | Medium |
| Web | TC-ACAD-007 | Classroom | Generate payment receipt | Student enrolled | 1. Open classroom<br>2. Select student<br>3. Generate receipt | Payment receipt generated | High |
| Web | TC-ACAD-008 | Classroom | Export classroom data | Classroom has students | 1. Click Export | Classroom data exported to Excel | Medium |
| Web | TC-ACAD-009 | Academic Setting | Configure class types | Admin logged in | 1. Click Settings<br>2. Add/Edit class types (After School, Intervention, ESP) | Class types configured | Medium |

---

## 11. Dashboard Module

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-DASH-001 | Dashboard | View dashboard | User logged in | 1. Click Dashboard | System displays overview with key metrics | High |
| Web | TC-DASH-002 | Dashboard | View leave summary | Leave data exists | 1. View leave section | System shows leave statistics by type | High |
| Web | TC-DASH-003 | Dashboard | View attendance summary | Attendance data exists | 1. View attendance section | System shows attendance overview | Medium |
| Web | TC-DASH-004 | Dashboard | Role-based view | Different user roles | 1. Login as different roles<br>2. View dashboard | Dashboard displays data based on user permission | High |
| Web | TC-DASH-005 | Dashboard | Filter by date range | Dashboard displayed | 1. Select date range | Dashboard updates to show filtered data | Medium |

---

## 12. Settings Module

### 12.1 Permission Setting

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-PERM-001 | Permission | View permission groups | Admin logged in | 1. Click Settings<br>2. Click Permissions | System displays permission groups | High |
| Web | TC-PERM-002 | Permission | Create permission group | Admin logged in | 1. Click Add Group<br>2. Enter name<br>3. Set permissions<br>4. Save | Permission group created | High |
| Web | TC-PERM-003 | Permission | Edit permission group | Group exists | 1. Open group<br>2. Modify permissions<br>3. Save | Permissions updated | High |
| Web | TC-PERM-004 | Permission | Delete permission group | Group exists, no users | 1. Delete group<br>2. Confirm | Group deleted | Medium |
| Web | TC-PERM-005 | Permission | Assign user to group | User and group exist | 1. Open user<br>2. Assign to group<br>3. Save | User assigned to permission group | High |
| Web | TC-PERM-006 | Permission | Set menu visibility | Editing group | 1. Toggle menu visibility (Show/Hide) | Menus shown/hidden for group members | High |
| Web | TC-PERM-007 | Permission | Set CRUD permissions | Editing group | 1. Set View/Edit/Delete for each menu | CRUD permissions applied | High |

### 12.2 Company Profile

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-COMP-001 | Company | View company profile | Admin logged in | 1. Click Company Profile | System displays company information | Medium |
| Web | TC-COMP-002 | Company | Edit company profile | Admin logged in | 1. Edit company details<br>2. Save | Company profile updated | Medium |
| Web | TC-COMP-003 | Company | Upload company logo | Admin logged in | 1. Click Upload Logo<br>2. Select image<br>3. Save | Logo updated | Low |

### 12.3 Leave Setting

| Platform | TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|----------|-------|---------|----------------------|--------------|------------|-----------------|----------|
| Web | TC-LSET-001 | Leave Setting | View leave types | Admin logged in | 1. Click Leave Settings | System displays leave type configurations | High |
| Web | TC-LSET-002 | Leave Setting | Add leave type | Admin logged in | 1. Click Add<br>2. Enter name, days allowed<br>3. Save | Leave type created | High |
| Web | TC-LSET-003 | Leave Setting | Edit leave type | Leave type exists | 1. Edit leave type<br>2. Modify days<br>3. Save | Leave type updated | High |
| Web | TC-LSET-004 | Leave Setting | Set leave cycle | Admin logged in | 1. Set cycle start/end dates<br>2. Save | Leave cycle configured (July 1 - June 30) | High |
| Web | TC-LSET-005 | Leave Setting | Set holidays | Admin logged in | 1. Click Holidays<br>2. Add holiday dates<br>3. Save | Holidays configured | Medium |
| Web | TC-LSET-006 | Leave Setting | Reset leave balances | Admin logged in | 1. Click Reset Cycle<br>2. Confirm | Leave balances reset for new cycle | High |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-12-16 | Foxbith QA | Initial comprehensive test cases |

---

*Document follows ISO/IEC 29110-5-1-2 Test Cases and Test Procedures requirements.*
