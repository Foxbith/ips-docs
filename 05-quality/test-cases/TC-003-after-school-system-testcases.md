# TC-003: After School System Test Cases

> ISO/IEC 29110-5-1-2 Work Product: Test Cases and Test Procedures

---

## Metadata

```yaml
id: TC-003
title: "After School System Test Cases"
type: "UAT"
project: "IPS - Pioneer International School Intranet System"
version: "1.0"
status: "Draft"
created: "2026-01-08"
updated: "2026-01-08"
author: "Claude"
requirements: ["FR-070", "FR-071", "FR-072"]
```

---

## 1. After School Module (FR-070)

### 1.1 Program Type Management

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-001 | Program Type | View program type list | User logged in with Academic permission | 1. Navigate to Academic menu<br>2. Click Program Types | System displays: After School, ESP, Summer School, Other | High |
| TC-AS-002 | Program Type | Add custom program type | Admin permission | 1. Click Add Program Type<br>2. Enter "Other" type name<br>3. Save | New program type created | Low |

### 1.2 After School Attendance Sheet

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-010 | Attendance Sheet | Create new attendance sheet | User has Academic permission | 1. Click After School menu<br>2. Click Create Attendance<br>3. Fill required fields<br>4. Save | Attendance sheet created successfully | High |
| TC-AS-011 | Attendance Sheet | Select student for attendance | Create form open | 1. Click Select Student<br>2. Search by name/ID<br>3. Select student | Student info auto-populated (name, ID, class, parent contact) | High |
| TC-AS-012 | Attendance Sheet | Select teacher for attendance | Create form open | 1. Click Select Teacher<br>2. Search by name<br>3. Select teacher | Teacher assigned to attendance sheet | High |
| TC-AS-013 | Attendance Sheet | Enter receipt information | Create form open | 1. Enter receipt date<br>2. Enter receipt number | Receipt info saved with validation for unique receipt number | High |
| TC-AS-014 | Attendance Sheet | Select subject | Create form open | 1. Click Subject dropdown<br>2. Select subject | Subject assigned to attendance | High |

### 1.3 Class Schedule Configuration

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-020 | Schedule | Select single day (Monday) | Create form open | 1. Check Monday checkbox | Class scheduled for Monday only | High |
| TC-AS-021 | Schedule | Select multiple days (Mon/Wed/Fri) | Create form open | 1. Check Mon, Wed, Fri checkboxes | Class scheduled for all selected days | High |
| TC-AS-022 | Schedule | Select Wed/Fri only | Create form open | 1. Check Wed, Fri checkboxes | Class scheduled for Wednesday and Friday | Medium |
| TC-AS-023 | Schedule | Verify only Mon/Wed/Fri available | Create form open | 1. View day selection options | Only Monday, Wednesday, Friday available (not Tue/Thu) | High |

### 1.4 Course Type Selection

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-030 | Course Type | Select full course (12 hours) | Create form open | 1. Select "Full Course"<br>2. Verify hours = 12 | Single attendance sheet created with 12 hours | High |
| TC-AS-031 | Course Type | Select split payment course | Create form open | 1. Select "Split Payment"<br>2. Verify 2 sheets created | Two attendance sheets created (6 hours each) | High |
| TC-AS-032 | Course Type | Select partial course (custom hours) | Create form open | 1. Select "Partial Course"<br>2. Enter 5 hours<br>3. Save | Attendance sheet created with 5 hours | High |
| TC-AS-033 | Course Type | Validate partial course hours | Create form open | 1. Select "Partial Course"<br>2. Enter 0 hours<br>3. Save | Validation error: hours must be > 0 | Medium |

### 1.5 Schedule Conflict Detection

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-040 | Conflict | Detect schedule conflict | Student has existing Monday class | 1. Create new attendance for same student<br>2. Select Monday<br>3. Save | Warning displayed about schedule conflict | High |
| TC-AS-041 | Conflict | Allow continuation despite conflict | Conflict warning shown | 1. View conflict warning<br>2. Click Continue | Attendance created despite conflict | High |
| TC-AS-042 | Conflict | Cancel due to conflict | Conflict warning shown | 1. View conflict warning<br>2. Click Cancel | Return to form without saving | Medium |

### 1.6 Attendance Recording

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-050 | Recording | Mark attendance present | Attendance sheet exists | 1. Open attendance sheet<br>2. Select date<br>3. Mark Present | Attendance recorded, hours deducted from remaining | High |
| TC-AS-051 | Recording | Mark attendance absent | Attendance sheet exists | 1. Open attendance sheet<br>2. Select date<br>3. Mark Absent | Absence recorded, hours remain unchanged | High |
| TC-AS-052 | Recording | View remaining hours | Attendance sheet exists | 1. Open attendance sheet | Display total hours, used hours, remaining hours | High |
| TC-AS-053 | Recording | Complete course notification | Remaining hours = 0 | 1. Mark final attendance | System shows course completion notification | Medium |

### 1.7 Attendance Sheet Output

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-AS-060 | Output | Print attendance sheet | Attendance sheet exists | 1. Click Print<br>2. View print preview | Print preview shows all required fields | High |
| TC-AS-061 | Output | Export attendance to PDF | Attendance sheet exists | 1. Click Export PDF | PDF generated with attendance details | Medium |
| TC-AS-062 | Output | View attendance sheet list | User has permission | 1. Navigate to After School<br>2. View list | Display all attendance sheets with filters | High |

---

## 2. English Support Program (ESP) Module (FR-071)

### 2.1 Term Management

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-ESP-001 | Term | View term list | User has Academic permission | 1. Navigate to ESP menu | Display Term 1, Term 2, Term 3 with date ranges | High |
| TC-ESP-002 | Term | Create ESP entry for Term 1 | ESP menu open | 1. Click Create<br>2. Select Term 1 (Sep-Nov)<br>3. Save | ESP entry created for Term 1 | High |
| TC-ESP-003 | Term | Create ESP entry for Term 2 | ESP menu open | 1. Click Create<br>2. Select Term 2 (Dec-Feb)<br>3. Save | ESP entry created for Term 2 | High |
| TC-ESP-004 | Term | Create ESP entry for Term 3 | ESP menu open | 1. Click Create<br>2. Select Term 3 (Mar-May)<br>3. Save | ESP entry created for Term 3 | High |

### 2.2 Class Group Management

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-ESP-010 | Class Group | Select class group Y3-Y9 | Create ESP form open | 1. Select Class Group dropdown | Only Y3-Y9 options available | High |
| TC-ESP-011 | Class Group | Assign teacher to group | Create form open | 1. Select Teacher dropdown<br>2. Choose teacher | Teacher assigned to ESP group | High |
| TC-ESP-012 | Class Group | Skip teacher assignment | Create form open | 1. Leave Teacher field empty<br>2. Save | ESP created without teacher (can assign later) | Medium |

### 2.3 Student Enrollment

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-ESP-020 | Enrollment | Add student to ESP | ESP entry exists | 1. Click Add Student<br>2. Search student<br>3. Enter payment info<br>4. Save | Student enrolled with payment record | High |
| TC-ESP-021 | Enrollment | Enter student payment info | Add student form open | 1. Enter payment date<br>2. Enter receipt number<br>3. Enter amount (7,500)<br>4. Add note | Payment info recorded for student | High |
| TC-ESP-022 | Enrollment | Add multiple students | ESP entry exists | 1. Add Student 1<br>2. Add Student 2<br>3. Add Student 3 | Multiple students enrolled in same ESP group | High |
| TC-ESP-023 | Enrollment | Validate required enrollment fields | Add student form open | 1. Leave required fields empty<br>2. Save | Validation errors shown | Medium |

### 2.4 Pricing and Payment Calculation

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-ESP-030 | Pricing | Verify term pricing default | Create ESP form | 1. View default price | Default = 7,500 THB per term | High |
| TC-ESP-031 | Pricing | Verify annual pricing calculation | Student has 3 terms | 1. View total payment | 22,500 THB (7,500 x 3 terms) | Medium |
| TC-ESP-032 | Pricing | Calculate teacher payment default | Teacher assigned, students enrolled | 1. View teacher payment | 1,500 THB per student per month (60% of 2,500) | High |
| TC-ESP-033 | Pricing | Modify base monthly rate | Admin permission | 1. Edit base rate<br>2. Enter new amount<br>3. Save | Teacher payment recalculated | Medium |
| TC-ESP-034 | Pricing | Modify teacher percentage | Admin permission | 1. Edit percentage<br>2. Enter new % (e.g., 70%)<br>3. Save | Teacher payment recalculated with new % | Medium |

### 2.5 Teacher Payment Sheet

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-ESP-040 | Payment Sheet | Generate teacher payment sheet | Teacher has enrolled students | 1. Navigate to ESP Payments<br>2. Select Teacher<br>3. Select Term<br>4. Generate | Payment sheet shows all students and calculated amounts | High |
| TC-ESP-041 | Payment Sheet | View payment by term | Payment data exists | 1. Filter by Term 1<br>2. View results | Display only Term 1 payments | High |
| TC-ESP-042 | Payment Sheet | Export payment sheet | Payment sheet generated | 1. Click Export | Payment sheet exported (Excel/PDF) | Medium |

### 2.6 ESP Reports

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-ESP-050 | Report | ESP student list - all | Students enrolled | 1. Navigate to Reports<br>2. Select ESP Students - All | Display all ESP enrolled students | High |
| TC-ESP-051 | Report | ESP students by teacher | Students assigned to teachers | 1. Select Report by Teacher<br>2. Choose teacher | Display students for selected teacher | High |
| TC-ESP-052 | Report | ESP students by class level | Students enrolled | 1. Select Report by Class Level<br>2. Choose level (e.g., Y5) | Display Y5 students in ESP | High |
| TC-ESP-053 | Report | ESP income - all | Payments recorded | 1. Select Income Report - All | Display total ESP income | High |
| TC-ESP-054 | Report | ESP income by date range | Payments recorded | 1. Select Income Report<br>2. Enter date range | Display income within date range | High |
| TC-ESP-055 | Report | ESP income by receipt | Payments recorded | 1. Select Income by Receipt<br>2. Enter receipt number | Display payment for specific receipt | Medium |
| TC-ESP-056 | Report | ESP payments - all | Teacher payments exist | 1. Select Payment Report - All | Display total payments to teachers | High |
| TC-ESP-057 | Report | ESP payments - monthly | Teacher payments exist | 1. Select Payment Report - Monthly<br>2. Select month | Display payments for selected month | High |

---

## 3. Summer School Module (FR-072)

### 3.1 Program Creation

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-SS-001 | Program | Create Summer School program | User has Academic permission | 1. Navigate to Summer School<br>2. Click Create Program<br>3. Enter year (2026)<br>4. Set date range<br>5. Set price<br>6. Save | Summer School program created | High |
| TC-SS-002 | Program | Set program date range | Create form open | 1. Select start date (e.g., June 1)<br>2. Select end date (e.g., July 15) | Date range saved | High |
| TC-SS-003 | Program | Set program price | Create form open | 1. Enter price amount | Price saved (variable by year) | High |
| TC-SS-004 | Program | Validate end date after start | Create form open | 1. Enter end date before start date<br>2. Save | Validation error shown | Medium |

### 3.2 Class Group Management

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-SS-010 | Class Group | Select class group K1-Y6 | Create form open | 1. Select Class Group dropdown | Only K1-Y6 options available | High |
| TC-SS-011 | Class Group | Assign teacher | Create form open | 1. Select Teacher | Teacher assigned | Medium |
| TC-SS-012 | Class Group | Skip teacher assignment | Create form open | 1. Leave Teacher empty<br>2. Save | Program created without teacher | Medium |

### 3.3 Student Enrollment

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-SS-020 | Enrollment | Enroll existing student | Summer program exists | 1. Click Add Student<br>2. Search existing student<br>3. Select student<br>4. Enter payment info<br>5. Save | Existing student enrolled | High |
| TC-SS-021 | Enrollment | Enroll new student (not in system) | Summer program exists | 1. Click Add New Student<br>2. Enter student name<br>3. Enter class level<br>4. Enter payment info<br>5. Save | New student added and enrolled | High |
| TC-SS-022 | Enrollment | Enter enrollment payment | Add student form | 1. Enter payment date<br>2. Enter receipt number<br>3. Enter amount | Payment recorded | High |

### 3.4 VAN Service Tracking

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-SS-030 | VAN | Enable VAN service for student | Student enrolled | 1. Check "Uses VAN Service"<br>2. Enter VAN payment date<br>3. Enter VAN receipt<br>4. Enter VAN amount<br>5. Save | VAN service recorded for student | High |
| TC-SS-031 | VAN | Disable VAN service | Student has VAN enabled | 1. Uncheck "Uses VAN Service"<br>2. Save | VAN service removed | Medium |
| TC-SS-032 | VAN | VAN payment required when enabled | VAN checkbox checked | 1. Enable VAN<br>2. Leave payment fields empty<br>3. Save | Validation error for VAN payment fields | Medium |

### 3.5 Summer School Reports

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-SS-040 | Report | Summer student list - all | Students enrolled | 1. Select Summer Students - All | Display all Summer School students | High |
| TC-SS-041 | Report | Summer students by teacher | Students assigned | 1. Select by Teacher<br>2. Choose teacher | Display teacher's students | High |
| TC-SS-042 | Report | Summer students by class | Students enrolled | 1. Select by Class Level<br>2. Choose level | Display students in selected level | High |
| TC-SS-043 | Report | Summer income - all | Payments recorded | 1. Select Income - All | Display total Summer School income | High |
| TC-SS-044 | Report | Summer income by date | Payments recorded | 1. Enter date range<br>2. Generate | Display income in date range | High |
| TC-SS-045 | Report | Summer income by receipt | Payments recorded | 1. Enter receipt number | Display payment for receipt | Medium |
| TC-SS-046 | Report | VAN service report | VAN services exist | 1. Select VAN Report | Display all students using VAN with payments | High |

---

## 4. Integration Test Cases

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-INT-001 | Integration | Student enrolled in multiple programs | Student exists | 1. Enroll in After School<br>2. Enroll in ESP<br>3. View student profile | All enrollments visible in student profile | High |
| TC-INT-002 | Integration | Teacher assigned multiple programs | Teacher exists | 1. Assign to After School<br>2. Assign to ESP<br>3. View teacher profile | All assignments visible | High |
| TC-INT-003 | Integration | Cross-program schedule conflict | Student in After School Mon | 1. Try to enroll same student in ESP Mon class | Schedule conflict warning displayed | Medium |
| TC-INT-004 | Integration | Payment summary across programs | Student has payments | 1. View student payment history | All program payments consolidated | Medium |

---

## 5. Edge Cases and Negative Tests

| TC ID | Feature | Test Case Description | Precondition | Test Steps | Expected Result | Priority |
|-------|---------|----------------------|--------------|------------|-----------------|----------|
| TC-NEG-001 | Validation | Duplicate receipt number | Receipt exists | 1. Enter existing receipt number<br>2. Save | Error: Receipt number must be unique | High |
| TC-NEG-002 | Validation | Invalid date format | Any form | 1. Enter invalid date<br>2. Save | Validation error for date | Medium |
| TC-NEG-003 | Validation | Negative payment amount | Payment form | 1. Enter -1000<br>2. Save | Error: Amount must be positive | Medium |
| TC-NEG-004 | Validation | Zero course hours | After School form | 1. Enter 0 hours<br>2. Save | Error: Hours must be > 0 | Medium |
| TC-NEG-005 | Permission | Unauthorized access | User without Academic permission | 1. Try to access After School menu | Access denied message | High |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-01-08 | Claude | Initial test cases for After School System |

---

*Template follows ISO/IEC 29110-5-1-2 Test Cases requirements.*
