# Project Plan: IPS - Phase 1

> ISO/IEC 29110-5-1-2 Work Product: Project Plan

---

## Metadata

```yaml
id: plan-phase1-ips
project: IPS
phase: 1
phase_name: "Pioneer International School Intranet System"
contract_ref: "CC20240711001"
version: "1.0.3"
status: "Active"
created: "2024-08-22"
last_modified: "2025-06-26"
author: "Danupha Mangnoi"
approved_by: "Danupha"
```

---

## 1. Plan Overview

### 1.1 Purpose
This project plan defines the activities, schedule, resources, and approach for Phase 1 of IPS (Pioneer International School Intranet System).

### 1.2 Phase Summary
| Aspect | Value |
|--------|-------|
| **Phase Name** | Pioneer International School Intranet System |
| **Duration** | 50+ weeks |
| **Start Date** | 2024-08-06 |
| **End Date** | 2025-08-29 (Target) |
| **Total Effort** | To be calculated |

### 1.3 Objectives
| # | Objective | Key Results |
|---|-----------|-------------|
| 1 | Develop comprehensive intranet system | Complete employee, student, and asset management modules |
| 2 | Implement UX/UI design | Complete all screens with client approval |
| 3 | Deploy functional system | UAT passed and go-live |

---

## 2. Scope Reference

### 2.1 Contract Reference
- **Contract:** CC20240711001 - Contract for design and development of Pioneer International School Intranet System

### 2.2 Deliverables Summary
| ID | Deliverable | Owner | Status |
|----|-------------|-------|--------|
| D1 | UX/UI Design - Login | Foxbith | Completed |
| D2 | UX/UI Design - Employee Module | Foxbith | Completed |
| D3 | UX/UI Design - Student Module | Foxbith | Completed |
| D4 | UX/UI Design - Asset Module | Foxbith | Completed |
| D5 | UX/UI Design - Form Module | Foxbith | Completed |
| D6 | UX/UI Design - Product Module | Foxbith | Completed |
| D7 | UX/UI Design - Stationary Module | Foxbith | Completed |
| D8 | UX/UI Design - Setting Module | Foxbith | Completed |
| D9 | Frontend Development | Foxbith | In Progress |
| D10 | Backend Development | Foxbith | In Progress |
| D11 | UAT Testing | IPS | In Progress |

### 2.3 Requirements Reference
| Category | Count | Location |
|----------|-------|----------|
| Functional | 14 Main Features | `02-requirements/specifications/functional-requirements/` |
| Interface | Multiple | `02-requirements/specifications/interface-requirements/` |
| Non-Functional | Multiple | `02-requirements/specifications/non-functional-requirements/` |

---

## 3. Work Breakdown Structure (WBS)

### 3.1 Major Work Packages
| WP | Work Package | Description | Owner | Status |
|----|--------------|-------------|-------|--------|
| WP1 | Data Collection & Structure | Requirement gathering, data structure planning | Foxbith | Completed |
| WP2 | UX/UI Design | Design all screens and flows | Foxbith | Completed |
| WP3 | Frontend Development | Develop user interface | Foxbith | In Progress |
| WP4 | Backend Development | Develop API and business logic | Foxbith | In Progress |
| WP5 | Testing | UAT and bug fixing | Foxbith/IPS | In Progress |
| WP6 | Deployment | Production deployment | Foxbith | Pending |

### 3.2 Feature Breakdown
| No. | Feature | Description |
|-----|---------|-------------|
| 1 | Login (LogIn) | Google authentication via G Suite @ips.ac.th |
| 2 | Employee Module | Time attendance, leave management, profile, training |
| 3 | Student Module | Student information, import/export, status management |
| 4 | Asset Module | Asset management, tracking, status |
| 5 | Form Module | 5 form types: Present, CCTV, Leave, Stationary, Booking |
| 6 | Product Module | Product management, sales, inventory |
| 7 | Stationary Module | Stationary management, withdrawal |
| 8 | Academic Module | Classroom, After School, Intervention, ESP |
| 9 | Dashboard | Reports and analytics |
| 10 | Settings | Permissions, company profile, leave settings |

---

## 4. Schedule

### 4.1 UX/UI Design Schedule
| No. | Task | Owner | Start Date | Due Date | Status |
|-----|------|-------|------------|----------|--------|
| 1.1 | Requirement Gathering | Foxbith | 2024-08-06 | 2024-08-09 | Completed |
| 1.2 | Data Structure Planning | Foxbith | 2024-08-07 | 2024-08-16 | Completed |
| 2.1 | Login Design | Foxbith | 2024-08-19 | 2024-08-30 | Completed |
| 2.2 | Employee Menu Design | Foxbith | 2024-08-19 | 2024-08-30 | Completed |
| 2.3 | Student Menu Design | Foxbith | 2024-08-23 | 2024-08-30 | Completed |
| 2.4 | Asset Menu Design | Foxbith | 2024-08-23 | 2024-08-30 | Completed |
| 2.5 | Form Menu Design | Foxbith | 2024-08-23 | 2024-08-30 | Completed |
| 2.6 | Product Menu Design | Foxbith | 2024-09-02 | 2024-08-30 | Completed |
| 2.7 | Stationary Menu Design | Foxbith | 2024-09-02 | 2024-08-30 | Completed |
| 2.1 | Setting Menu Design | Foxbith | 2024-09-02 | 2024-08-30 | Completed |

### 4.2 Development Milestones
| Milestone | Date | Status |
|-----------|------|--------|
| UI Review 1 | Various | Completed |
| UI Review 2 | Various | Completed |
| UI Review 3 | Various | Completed |
| Development - Classroom Payment & Menu | 2025-05-02 - 2025-06-19 | Completed |
| Development - Student, Payment, Export | 2025-06-20 - 2025-08-11 | In Progress |
| UAT 2 | 2025-09-09 - 2025-09-22 | Completed |
| Bug Fix & Final UAT | 2025-08-14 - 2025-08-29 | In Progress |

---

## 5. Resources

### 5.1 Team Allocation
| Role | Name | Responsibility |
|------|------|----------------|
| Project Coordinator | Danupha Mangnoi | Project management, documentation |
| Development Team | Foxbith | Design, development, testing |
| Developer | Nitipum | Development |

### 5.2 Tools & Infrastructure
| Category | Tool | Purpose |
|----------|------|---------|
| Design | Canva | UI/UX Design |
| Project Management | Excel/Spreadsheet | Task tracking |
| Communication | Email/Meeting | Bi-weekly updates |

---

## 6. Quality Plan

### 6.1 Review Gates
| Gate | When | Criteria | Approver |
|------|------|----------|----------|
| UI Review 1 | After initial design | All screens complete | IPS |
| UI Review 2 | After feedback | Feedback incorporated | IPS |
| UI Review 3 | Before development | Final approval | IPS |
| UAT | Before go-live | All test cases passed | IPS |

### 6.2 Testing Strategy
| Test Type | Coverage | Responsibility |
|-----------|----------|----------------|
| Unit Testing | All features | Foxbith |
| UAT | All user flows | IPS |

---

## 7. Communication Plan

### 7.1 Stakeholder Communication
| Stakeholder | Information Needs | Frequency | Method |
|-------------|-------------------|-----------|--------|
| IPS Client | Progress, blockers | Bi-weekly | Meeting/Online |
| Dev Team | Tasks, priorities | Weekly | Internal |

### 7.2 Meeting Records
- `01-planning/meeting-record/` - All bi-weekly meeting records

---

## 8. Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| V1.0.0 | 2024-08-22 | Danupha | Initial timeline |
| V1.0.1 | - | Danupha | Timeline adjustment |
| V1.0.2 | - | Danupha | Timeline adjustment |
| V1.0.3 | 2025-06-26 | Nitipum | Add new timeline and adjust timeline to be present |

---

*Document follows ISO/IEC 29110-5-1-2 Project Plan requirements.*
