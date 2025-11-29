# Test Report: [VERSION/RELEASE]

> ISO/IEC 29110-5-1-2 Work Product: Test Report

---

## Metadata

```yaml
id: test-report-[VERSION]
project: "[PROJECT_NAME]"
phase: [N]
version: "[X.Y.Z]"
test_period: "YYYY-MM-DD to YYYY-MM-DD"
report_date: "YYYY-MM-DD"
prepared_by: "[NAME]"
status: "[Draft/Final]"
```

---

## 1. Executive Summary

### 1.1 Overview
| Attribute | Value |
|-----------|-------|
| **Release Version** | [X.Y.Z] |
| **Test Period** | [Start] to [End] |
| **Test Environment** | [Staging/UAT] |
| **Build Tested** | [Build #/Commit] |

### 1.2 Summary Results
| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Test Cases Executed | [X] | [X] | - |
| Pass Rate | > [X]% | [X]% | [Pass/Fail] |
| Critical Defects | 0 | [X] | [Pass/Fail] |
| High Defects | 0 | [X] | [Pass/Fail] |

### 1.3 Release Recommendation
| Recommendation | Notes |
|----------------|-------|
| [ ] **Go** | All criteria met |
| [ ] **Go with Conditions** | [Conditions] |
| [ ] **No-Go** | [Blockers] |

---

## 2. Test Scope

### 2.1 In Scope
| Area | Description | Coverage |
|------|-------------|----------|
| [Feature 1] | [Description] | [X] test cases |
| [Feature 2] | [Description] | [X] test cases |
| [Regression] | [Description] | [X] test cases |

### 2.2 Out of Scope
| Area | Reason |
|------|--------|
| [Feature X] | [Not changed in this release] |
| [Performance] | [Separate test cycle] |

---

## 3. Test Execution Summary

### 3.1 By Test Type
| Test Type | Total | Passed | Failed | Blocked | Skipped | Pass Rate |
|-----------|-------|--------|--------|---------|---------|-----------|
| Smoke | [X] | [X] | [X] | [X] | [X] | [X]% |
| Functional | [X] | [X] | [X] | [X] | [X] | [X]% |
| Regression | [X] | [X] | [X] | [X] | [X] | [X]% |
| Integration | [X] | [X] | [X] | [X] | [X] | [X]% |
| E2E | [X] | [X] | [X] | [X] | [X] | [X]% |
| **Total** | **[X]** | **[X]** | **[X]** | **[X]** | **[X]** | **[X]%** |

### 3.2 By Priority
| Priority | Total | Passed | Failed | Pass Rate |
|----------|-------|--------|--------|-----------|
| P1 (Critical) | [X] | [X] | [X] | [X]% |
| P2 (High) | [X] | [X] | [X] | [X]% |
| P3 (Medium) | [X] | [X] | [X] | [X]% |

### 3.3 By Feature
| Feature | Test Cases | Passed | Failed | Pass Rate |
|---------|------------|--------|--------|-----------|
| [Feature 1] | [X] | [X] | [X] | [X]% |
| [Feature 2] | [X] | [X] | [X] | [X]% |
| [Feature 3] | [X] | [X] | [X] | [X]% |

---

## 4. Defect Summary

### 4.1 Defect Statistics
| Severity | Found | Fixed | Open | Deferred |
|----------|-------|-------|------|----------|
| Critical | [X] | [X] | [X] | [X] |
| High | [X] | [X] | [X] | [X] |
| Medium | [X] | [X] | [X] | [X] |
| Low | [X] | [X] | [X] | [X] |
| **Total** | **[X]** | **[X]** | **[X]** | **[X]** |

### 4.2 Critical/High Defects
| Defect ID | Title | Severity | Status | Impact |
|-----------|-------|----------|--------|--------|
| [DEF-001] | [Title] | Critical | [Status] | [Impact on release] |
| [DEF-002] | [Title] | High | [Status] | [Impact on release] |

### 4.3 Deferred Defects
| Defect ID | Title | Severity | Reason | Target |
|-----------|-------|----------|--------|--------|
| [DEF-XXX] | [Title] | [Sev] | [Reason] | [Version] |

---

## 5. Requirements Coverage

### 5.1 Coverage Summary
| Category | Total Reqs | Tested | Passed | Coverage |
|----------|------------|--------|--------|----------|
| Functional | [X] | [X] | [X] | [X]% |
| Interface | [X] | [X] | [X] | [X]% |
| Non-Functional | [X] | [X] | [X] | [X]% |

### 5.2 Untested Requirements
| Req ID | Reason |
|--------|--------|
| [FR-XXX] | [Environment not ready] |
| [NFR-YYY] | [Deferred to next release] |

---

## 6. Test Environment

### 6.1 Environment Details
| Attribute | Value |
|-----------|-------|
| Environment | [Staging/UAT] |
| URL | [Environment URL] |
| Database | [DB version and config] |
| Browser(s) | [Tested browsers] |
| Mobile | [Tested devices] |

### 6.2 Environment Issues
| Issue | Impact | Resolution |
|-------|--------|------------|
| [Issue 1] | [Tests blocked] | [How resolved] |

---

## 7. Automation Results

### 7.1 Automated Test Summary
| Category | Total | Passed | Failed | Flaky |
|----------|-------|--------|--------|-------|
| Unit Tests | [X] | [X] | [X] | [X] |
| Integration | [X] | [X] | [X] | [X] |
| E2E | [X] | [X] | [X] | [X] |

### 7.2 Code Coverage
| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Line Coverage | > [X]% | [X]% | [Pass/Fail] |
| Branch Coverage | > [X]% | [X]% | [Pass/Fail] |

---

## 8. Performance Results (if applicable)

| Metric | Target | Actual | Status |
|--------|--------|--------|--------|
| Avg Response Time | < [X]ms | [X]ms | [Pass/Fail] |
| P95 Response Time | < [X]ms | [X]ms | [Pass/Fail] |
| Throughput | > [X] rps | [X] rps | [Pass/Fail] |
| Error Rate | < [X]% | [X]% | [Pass/Fail] |

---

## 9. Risks and Issues

### 9.1 Open Risks
| Risk | Impact | Mitigation |
|------|--------|------------|
| [Risk 1] | [Impact] | [Action] |

### 9.2 Open Issues
| Issue | Impact | Owner | Status |
|-------|--------|-------|--------|
| [Issue 1] | [Impact] | [Name] | [Status] |

---

## 10. Exit Criteria Evaluation

| Criterion | Target | Actual | Met? |
|-----------|--------|--------|------|
| All P1 tests executed | 100% | [X]% | [ ] |
| All P1 tests passed | 100% | [X]% | [ ] |
| No open critical defects | 0 | [X] | [ ] |
| No open high defects | 0 | [X] | [ ] |
| Code coverage | > [X]% | [X]% | [ ] |

---

## 11. Conclusion

### 11.1 Summary
[Summary of test execution and overall quality assessment]

### 11.2 Recommendations
1. [Recommendation 1]
2. [Recommendation 2]

### 11.3 Lessons Learned
| Area | Observation | Improvement |
|------|-------------|-------------|
| [Area] | [What happened] | [How to improve] |

---

## 12. Sign-off

| Role | Name | Decision | Date |
|------|------|----------|------|
| QA Lead | [Name] | [ ] Approve [ ] Reject | YYYY-MM-DD |
| PM | [Name] | [ ] Approve [ ] Reject | YYYY-MM-DD |
| Tech Lead | [Name] | [ ] Approve [ ] Reject | YYYY-MM-DD |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial report |

---

*Template follows ISO/IEC 29110-5-1-2 Test Report requirements.*
