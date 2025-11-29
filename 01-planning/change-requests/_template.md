# Change Request: [CR_TITLE]

> ISO/IEC 29110-5-1-2 Work Product: Change Request

---

## Metadata

```yaml
id: CR-[XXX]-[short-name]
project: "[PROJECT_NAME]"
phase: [N]
contract_ref: "SOW-phase[N]-[DATE]"
version: "1.0"
status: "Submitted"
priority: "[Critical/High/Medium/Low]"
type: "[Scope/Schedule/Budget/Technical]"
created: "YYYY-MM-DD"
requested_by: "[NAME]"
assigned_to: "[NAME]"
```

---

## 1. Change Request Summary

### 1.1 Title
[Short descriptive title of the change]

### 1.2 Description
[Detailed description of what change is being requested and why]

### 1.3 Business Justification
[Why is this change needed? What business value does it provide?]

---

## 2. Change Classification

| Attribute | Value |
|-----------|-------|
| **Type** | [ ] Scope [ ] Schedule [ ] Budget [ ] Technical [ ] Other |
| **Category** | [ ] New Feature [ ] Enhancement [ ] Bug Fix [ ] Requirement Change |
| **Priority** | [ ] Critical [ ] High [ ] Medium [ ] Low |
| **Urgency** | [ ] Immediate [ ] This Sprint [ ] Next Sprint [ ] Backlog |

---

## 3. Impact Analysis

### 3.1 Scope Impact
| Aspect | Current State | Proposed Change | Delta |
|--------|---------------|-----------------|-------|
| Requirements | [X] FRs | [+/-X] FRs | [Description] |
| Features | [List] | [List] | [What changes] |
| Deliverables | [List] | [List] | [What changes] |

### 3.2 Schedule Impact
| Milestone | Original Date | New Date | Variance |
|-----------|---------------|----------|----------|
| [Milestone] | YYYY-MM-DD | YYYY-MM-DD | [+/-X days] |

### 3.3 Effort Impact
| Role | Original Effort | Additional Effort | New Total |
|------|-----------------|-------------------|-----------|
| Development | [X] hours | [+X] hours | [X] hours |
| QA | [X] hours | [+X] hours | [X] hours |
| Design | [X] hours | [+X] hours | [X] hours |
| **Total** | **[X] hours** | **[+X] hours** | **[X] hours** |

### 3.4 Cost Impact
| Item | Amount | Notes |
|------|--------|-------|
| Additional Development | [Amount] | |
| Additional Testing | [Amount] | |
| Infrastructure | [Amount] | |
| **Total** | **[Amount]** | |

### 3.5 Risk Impact
| New/Increased Risk | Probability | Impact | Mitigation |
|--------------------|-------------|--------|------------|
| [Risk 1] | H/M/L | H/M/L | [Action] |

---

## 4. Affected Artifacts

### 4.1 Requirements
| Requirement ID | Change Type | Description |
|----------------|-------------|-------------|
| [FR-XXX] | [Add/Modify/Remove] | [Description] |
| [NFR-XXX] | [Add/Modify/Remove] | [Description] |

### 4.2 Design
| Document | Change Type | Description |
|----------|-------------|-------------|
| [Component] | [Add/Modify/Remove] | [Description] |

### 4.3 Code
| Component/Module | Change Type | Description |
|------------------|-------------|-------------|
| [Module] | [Add/Modify/Remove] | [Description] |

### 4.4 Tests
| Test Type | Change | Description |
|-----------|--------|-------------|
| [Unit/Integration/E2E] | [Add/Modify] | [Description] |

---

## 5. Alternatives Considered

| # | Alternative | Pros | Cons | Recommendation |
|---|-------------|------|------|----------------|
| 1 | [Alternative 1] | [Pros] | [Cons] | [ ] Recommended |
| 2 | [Alternative 2] | [Pros] | [Cons] | [ ] Recommended |
| 3 | Do Nothing | No cost/risk | [Impact of not changing] | [ ] Recommended |

---

## 6. Implementation Plan

### 6.1 High-Level Approach
[Describe how the change will be implemented]

### 6.2 Tasks
| # | Task | Owner | Effort | Sprint |
|---|------|-------|--------|--------|
| 1 | [Task 1] | [Name] | [X]h | Sprint [N] |
| 2 | [Task 2] | [Name] | [X]h | Sprint [N] |

### 6.3 Dependencies
- [ ] [Dependency 1]
- [ ] [Dependency 2]

---

## 7. Approval Workflow

### 7.1 Approval Authority
| Change Size | Authority | Required Approvers |
|-------------|-----------|-------------------|
| < [X] hours | Tech Lead | Tech Lead |
| [X]-[Y] hours | PM | PM + Tech Lead |
| > [Y] hours | Steering | PM + Client PM + Sponsor |

### 7.2 Approval Status

| Step | Approver | Decision | Date | Comments |
|------|----------|----------|------|----------|
| Technical Review | [Name] | [ ] Approved [ ] Rejected [ ] Pending | | |
| PM Review | [Name] | [ ] Approved [ ] Rejected [ ] Pending | | |
| Client Approval | [Name] | [ ] Approved [ ] Rejected [ ] Pending | | |
| Steering Approval | [Name] | [ ] Approved [ ] Rejected [ ] Pending | | |

### 7.3 Final Decision
| Field | Value |
|-------|-------|
| **Decision** | [ ] Approved [ ] Rejected [ ] Deferred |
| **Decision Date** | YYYY-MM-DD |
| **Decision By** | [Name/Role] |
| **Conditions** | [Any conditions for approval] |

---

## 8. Implementation Tracking

### 8.1 Implementation Status
| Status | Date | Notes |
|--------|------|-------|
| [ ] Approved | YYYY-MM-DD | |
| [ ] In Progress | YYYY-MM-DD | |
| [ ] Completed | YYYY-MM-DD | |
| [ ] Verified | YYYY-MM-DD | |
| [ ] Closed | YYYY-MM-DD | |

### 8.2 Verification
| Criterion | Status | Verified By | Date |
|-----------|--------|-------------|------|
| [Criterion 1] | [ ] Pass [ ] Fail | [Name] | |
| [Criterion 2] | [ ] Pass [ ] Fail | [Name] | |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial submission |
| 1.1 | YYYY-MM-DD | [Name] | Updated after review |

---

## References

- Contract: `contracts/SOW-phase[N]-[DATE].md`
- Project Plan: `project-plans/plan-phase[N]-[NAME].md`
- Related CRs: `CR-XXX`, `CR-YYY`

---

*Template follows ISO/IEC 29110-5-1-2 Change Request requirements.*
