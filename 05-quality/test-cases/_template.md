# TC-[XXX]: [Test Case Title]

> ISO/IEC 29110-5-1-2 Work Product: Test Cases

---

## Metadata

```yaml
id: TC-[XXX]
title: "[Test Case Title]"
type: "[Unit/Integration/E2E/Performance/Security]"
priority: "[P1/P2/P3]"
phase: [N]
requirements: ["FR-XXX", "FR-YYY"]
version: "1.0"
status: "Draft"
created: "YYYY-MM-DD"
last_modified: "YYYY-MM-DD"
author: "[NAME]"
automated: "[Yes/No/Partial]"
automation_id: "[test file path or ID]"
```

---

## 1. Test Case Summary

### 1.1 Objective
[What this test case validates]

### 1.2 Description
[Brief description of the test scenario and what it covers]

### 1.3 Requirements Covered
| Requirement | Description |
|-------------|-------------|
| [FR-XXX] | [Requirement summary] |
| [FR-YYY] | [Requirement summary] |

---

## 2. Preconditions

- [ ] [Precondition 1 - e.g., User is logged in]
- [ ] [Precondition 2 - e.g., Test data exists]
- [ ] [Precondition 3 - e.g., Feature flag enabled]

### Test Data Requirements
| Data | Value/Description | Source |
|------|-------------------|--------|
| [User] | [Test user credentials] | [Seeded/Created] |
| [Entity] | [Required entity] | [Seeded/Created] |

---

## 3. Test Steps

| Step | Action | Expected Result | Actual Result | Status |
|------|--------|-----------------|---------------|--------|
| 1 | [Action to perform] | [Expected outcome] | | [ ] Pass [ ] Fail |
| 2 | [Action to perform] | [Expected outcome] | | [ ] Pass [ ] Fail |
| 3 | [Action to perform] | [Expected outcome] | | [ ] Pass [ ] Fail |
| 4 | [Action to perform] | [Expected outcome] | | [ ] Pass [ ] Fail |
| 5 | [Action to perform] | [Expected outcome] | | [ ] Pass [ ] Fail |

---

## 4. Test Data

### 4.1 Input Data
| Field | Value | Notes |
|-------|-------|-------|
| [field1] | [value] | |
| [field2] | [value] | |

### 4.2 Expected Output
| Field | Expected Value |
|-------|----------------|
| [field1] | [expected] |
| [field2] | [expected] |

---

## 5. Postconditions

After successful test execution:
- [ ] [Postcondition 1 - e.g., Record created in database]
- [ ] [Postcondition 2 - e.g., Email sent]
- [ ] [Postcondition 3 - e.g., Audit log entry created]

### Cleanup
- [ ] [Cleanup action 1 - e.g., Delete test user]
- [ ] [Cleanup action 2 - e.g., Reset data]

---

## 6. Edge Cases / Variations

| Variation | Description | Expected Result |
|-----------|-------------|-----------------|
| [Variation 1] | [Empty input] | [Validation error] |
| [Variation 2] | [Max length input] | [Accepted] |
| [Variation 3] | [Invalid format] | [Error message] |

---

## 7. Execution History

| Run # | Date | Tester | Environment | Result | Defects |
|-------|------|--------|-------------|--------|---------|
| 1 | YYYY-MM-DD | [Name] | [Staging] | [Pass/Fail] | [DEF-XXX] |
| 2 | YYYY-MM-DD | [Name] | [Staging] | [Pass/Fail] | - |

---

## 8. Notes

### Known Issues
- [Any known issues that affect this test]

### Assumptions
- [Assumption 1]
- [Assumption 2]

### Dependencies
- [TC-YYY] - [This test should run after TC-YYY]

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial test case |

---

*Template follows ISO/IEC 29110-5-1-2 Test Cases requirements.*
