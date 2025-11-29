# Project Plan: [PROJECT_NAME] - Phase [N]

> ISO/IEC 29110-5-1-2 Work Product: Project Plan

---

## Metadata

```yaml
id: plan-phase[N]-[NAME]
project: [PROJECT_NAME]
phase: [N]
phase_name: "[PHASE_NAME]"
contract_ref: "SOW-phase[N]-[DATE]"
version: "1.0"
status: "Draft"
created: "YYYY-MM-DD"
last_modified: "YYYY-MM-DD"
author: "[NAME]"
approved_by: "[PENDING]"
```

---

## 1. Plan Overview

### 1.1 Purpose
This project plan defines the activities, schedule, resources, and approach for Phase [N] of [PROJECT_NAME].

### 1.2 Phase Summary
| Aspect | Value |
|--------|-------|
| **Phase Name** | [PHASE_NAME] |
| **Duration** | [X] weeks |
| **Start Date** | YYYY-MM-DD |
| **End Date** | YYYY-MM-DD |
| **Total Effort** | [X] person-days |

### 1.3 Objectives
| # | Objective | Key Results |
|---|-----------|-------------|
| 1 | [Objective] | [Measurable outcome] |
| 2 | [Objective] | [Measurable outcome] |

---

## 2. Scope Reference

### 2.1 Contract Reference
- **SOW:** `contracts/SOW-phase[N]-[DATE].md`
- **Scope Definition:** `scope-definitions/scope-phase[N]-baseline.md`

### 2.2 Deliverables Summary
| ID | Deliverable | Owner | Due Date |
|----|-------------|-------|----------|
| D1 | [Name] | [Role] | YYYY-MM-DD |
| D2 | [Name] | [Role] | YYYY-MM-DD |

### 2.3 Requirements Reference
| Category | Count | Location |
|----------|-------|----------|
| Functional | [X] | `02-requirements/specifications/functional-requirements/` |
| Interface | [X] | `02-requirements/specifications/interface-requirements/` |
| Non-Functional | [X] | `02-requirements/specifications/non-functional-requirements/` |

---

## 3. Work Breakdown Structure (WBS)

### 3.1 Major Work Packages
| WP | Work Package | Description | Effort | Owner |
|----|--------------|-------------|--------|-------|
| WP1 | Project Setup | Environment, tools, access | [X]d | [Role] |
| WP2 | Requirements Analysis | Finalize and approve specs | [X]d | [Role] |
| WP3 | Design | Architecture, API, UX | [X]d | [Role] |
| WP4 | Development | Sprint 1-N | [X]d | [Role] |
| WP5 | Testing | Unit, Integration, UAT | [X]d | [Role] |
| WP6 | Deployment | Release to production | [X]d | [Role] |
| WP7 | Documentation | User guide, ops manual | [X]d | [Role] |

### 3.2 Sprint Plan
| Sprint | Dates | Focus | Stories | Points |
|--------|-------|-------|---------|--------|
| Sprint 1 | DD-MMM to DD-MMM | [Focus area] | [X] | [X] |
| Sprint 2 | DD-MMM to DD-MMM | [Focus area] | [X] | [X] |
| Sprint 3 | DD-MMM to DD-MMM | [Focus area] | [X] | [X] |

---

## 4. Schedule

### 4.1 Milestone Schedule
| Milestone | Date | Criteria | Status |
|-----------|------|----------|--------|
| M0: Kickoff | YYYY-MM-DD | Team onboarded, env ready | [ ] |
| M1: Requirements Approved | YYYY-MM-DD | All specs signed off | [ ] |
| M2: Design Complete | YYYY-MM-DD | Architecture reviewed | [ ] |
| M3: Development Complete | YYYY-MM-DD | All features implemented | [ ] |
| M4: UAT Complete | YYYY-MM-DD | Client acceptance | [ ] |
| M5: Go-Live | YYYY-MM-DD | Production deployment | [ ] |

### 4.2 Gantt Chart Reference
```
Week:     1    2    3    4    5    6    7    8    9   10
         ├────┼────┼────┼────┼────┼────┼────┼────┼────┤
Setup    ████
Reqs     ░░░░████
Design        ░░░░████████
Dev                  ░░░░████████████████
Test                           ░░░░░░░░████████
Deploy                                      ░░░░████
Docs         ░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░░████

████ = Primary focus
░░░░ = Ongoing/Support
```

---

## 5. Resources

### 5.1 Team Allocation
| Role | Name | Allocation | Rate | Start | End |
|------|------|------------|------|-------|-----|
| Project Manager | [Name] | [X]% | [Rate] | YYYY-MM-DD | YYYY-MM-DD |
| Tech Lead | [Name] | [X]% | [Rate] | YYYY-MM-DD | YYYY-MM-DD |
| Senior Developer | [Name] | [X]% | [Rate] | YYYY-MM-DD | YYYY-MM-DD |
| Developer | [Name] | [X]% | [Rate] | YYYY-MM-DD | YYYY-MM-DD |
| QA Engineer | [Name] | [X]% | [Rate] | YYYY-MM-DD | YYYY-MM-DD |

### 5.2 Capacity Calculation
| Role | Days Available | Meetings/Overhead | Net Capacity |
|------|----------------|-------------------|--------------|
| [Role] | [X] days | [X] days | [X] days |

### 5.3 Tools & Infrastructure
| Category | Tool | Purpose | Owner |
|----------|------|---------|-------|
| Version Control | GitHub | Code repository | [Team] |
| Project Management | [Tool] | Task tracking | PM |
| CI/CD | [Tool] | Deployment | DevOps |
| Communication | [Tool] | Team chat | All |

---

## 6. Quality Plan

### 6.1 Quality Objectives
| Metric | Target | Measurement |
|--------|--------|-------------|
| Code Coverage | > [X]% | SonarQube |
| Defect Density | < [X] per KLOC | Bug tracking |
| Sprint Velocity | [X] points/sprint | Burndown |
| Customer Satisfaction | > [X]/5 | Survey |

### 6.2 Review Gates
| Gate | When | Criteria | Approver |
|------|------|----------|----------|
| Requirements Review | Before design | All specs complete | PO |
| Design Review | Before dev | Architecture approved | Tech Lead |
| Code Review | Every PR | Review checklist passed | Peer |
| UAT Sign-off | Before go-live | All test cases passed | Client |

### 6.3 Testing Strategy
| Test Type | Coverage | Responsibility | Tools |
|-----------|----------|----------------|-------|
| Unit | [X]% | Developers | Jest/pytest |
| Integration | Critical paths | QA | [Tool] |
| E2E | User journeys | QA | Playwright |
| UAT | All features | Client | Manual |

---

## 7. Risk Management

### 7.1 Risk Register
| ID | Risk | Probability | Impact | Score | Mitigation | Owner | Status |
|----|------|-------------|--------|-------|------------|-------|--------|
| R1 | [Risk] | H/M/L | H/M/L | [1-9] | [Action] | [Name] | Open |
| R2 | [Risk] | H/M/L | H/M/L | [1-9] | [Action] | [Name] | Open |

### 7.2 Contingency Plan
| Trigger | Action | Owner |
|---------|--------|-------|
| [Trigger condition] | [Contingency action] | [Name] |

---

## 8. Communication Plan

### 8.1 Stakeholder Communication
| Stakeholder | Information Needs | Frequency | Method | Owner |
|-------------|-------------------|-----------|--------|-------|
| Client PM | Progress, blockers | Weekly | Meeting | PM |
| Steering Committee | Status, risks | Bi-weekly | Report | PM |
| Dev Team | Tasks, priorities | Daily | Standup | TL |

### 8.2 Reporting
| Report | Frequency | Audience | Content |
|--------|-----------|----------|---------|
| Sprint Report | Per sprint | All | Progress, velocity, blockers |
| Status Report | Weekly | Client | Milestones, risks, issues |
| Steering Report | Bi-weekly | Executives | Summary, decisions needed |

---

## 9. Change Management

### 9.1 Change Control Process
1. Change Request submitted → `change-requests/CR-XXX-[name].md`
2. Impact assessment by Tech Lead
3. Approval by Project Manager / Steering
4. Update scope and plan
5. Communicate to team

### 9.2 Change Authority
| Change Type | Authority | Response Time |
|-------------|-----------|---------------|
| Minor (< [X] hours) | Tech Lead | 1 day |
| Medium ([X]-[Y] hours) | PM | 3 days |
| Major (> [Y] hours) | Steering | 1 week |

---

## 10. Monitoring & Control

### 10.1 Key Performance Indicators
| KPI | Target | Actual | Status |
|-----|--------|--------|--------|
| Sprint Velocity | [X] pts | - | - |
| Defect Escape Rate | < [X]% | - | - |
| Schedule Variance | < [X]% | - | - |
| Budget Variance | < [X]% | - | - |

### 10.2 Progress Tracking
- Sprint Reports: `progress-tracking/sprint-[DATE].md`
- Meeting Records: `meeting-record/[DATE].md`

---

## 11. Approvals

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Project Manager | [Name] | _____________ | YYYY-MM-DD |
| Tech Lead | [Name] | _____________ | YYYY-MM-DD |
| Client PM | [Name] | _____________ | YYYY-MM-DD |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 0.1 | YYYY-MM-DD | [Name] | Initial draft |
| 1.0 | YYYY-MM-DD | [Name] | Approved |

---

*Template follows ISO/IEC 29110-5-1-2 Project Plan requirements.*
