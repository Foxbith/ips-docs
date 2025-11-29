# Code Review Record: [PR/MR Title]

> ISO/IEC 29110-5-1-2 Work Product: Verification Results - Code Review

---

## Metadata

```yaml
id: review-[DATE]-[SHORT_NAME]
project: "[PROJECT_NAME]"
phase: [N]
pr_number: "[PR-XXX]"
pr_url: "[GitHub/GitLab URL]"
review_date: "YYYY-MM-DD"
reviewer: "[NAME]"
author: "[NAME]"
status: "[Approved/Changes Requested/Needs Discussion]"
```

---

## 1. Review Summary

### 1.1 Change Overview
| Attribute | Value |
|-----------|-------|
| **PR Title** | [Title] |
| **Type** | [Feature/Bugfix/Refactor/Hotfix] |
| **Files Changed** | [X] files |
| **Lines Added** | +[X] |
| **Lines Removed** | -[X] |
| **Related Issue** | [Issue ID/Link] |

### 1.2 Requirements Covered
| Requirement | Description |
|-------------|-------------|
| [FR-XXX] | [Brief description] |
| [FR-YYY] | [Brief description] |

---

## 2. Review Checklist

### 2.1 Code Quality
| Check | Status | Notes |
|-------|--------|-------|
| Code is readable and self-documenting | [ ] Pass [ ] Fail [ ] N/A | |
| Functions/methods are appropriately sized | [ ] Pass [ ] Fail [ ] N/A | |
| No code duplication | [ ] Pass [ ] Fail [ ] N/A | |
| Naming conventions followed | [ ] Pass [ ] Fail [ ] N/A | |
| No dead/commented code | [ ] Pass [ ] Fail [ ] N/A | |

### 2.2 Design & Architecture
| Check | Status | Notes |
|-------|--------|-------|
| Follows established patterns | [ ] Pass [ ] Fail [ ] N/A | |
| SOLID principles applied | [ ] Pass [ ] Fail [ ] N/A | |
| Appropriate separation of concerns | [ ] Pass [ ] Fail [ ] N/A | |
| No unnecessary dependencies added | [ ] Pass [ ] Fail [ ] N/A | |

### 2.3 Functionality
| Check | Status | Notes |
|-------|--------|-------|
| Logic is correct | [ ] Pass [ ] Fail [ ] N/A | |
| Edge cases handled | [ ] Pass [ ] Fail [ ] N/A | |
| Error handling appropriate | [ ] Pass [ ] Fail [ ] N/A | |
| Null/undefined checks present | [ ] Pass [ ] Fail [ ] N/A | |

### 2.4 Testing
| Check | Status | Notes |
|-------|--------|-------|
| Unit tests added/updated | [ ] Pass [ ] Fail [ ] N/A | |
| Test coverage adequate | [ ] Pass [ ] Fail [ ] N/A | |
| Tests are meaningful | [ ] Pass [ ] Fail [ ] N/A | |
| Edge cases tested | [ ] Pass [ ] Fail [ ] N/A | |

### 2.5 Security
| Check | Status | Notes |
|-------|--------|-------|
| No hardcoded secrets | [ ] Pass [ ] Fail [ ] N/A | |
| Input validation present | [ ] Pass [ ] Fail [ ] N/A | |
| No SQL injection risks | [ ] Pass [ ] Fail [ ] N/A | |
| No XSS vulnerabilities | [ ] Pass [ ] Fail [ ] N/A | |
| Authentication/authorization correct | [ ] Pass [ ] Fail [ ] N/A | |

### 2.6 Performance
| Check | Status | Notes |
|-------|--------|-------|
| No obvious performance issues | [ ] Pass [ ] Fail [ ] N/A | |
| Database queries optimized | [ ] Pass [ ] Fail [ ] N/A | |
| No N+1 query issues | [ ] Pass [ ] Fail [ ] N/A | |
| Caching considered where appropriate | [ ] Pass [ ] Fail [ ] N/A | |

### 2.7 Documentation
| Check | Status | Notes |
|-------|--------|-------|
| Complex logic commented | [ ] Pass [ ] Fail [ ] N/A | |
| API documentation updated | [ ] Pass [ ] Fail [ ] N/A | |
| README updated if needed | [ ] Pass [ ] Fail [ ] N/A | |

---

## 3. Findings

### 3.1 Critical Issues (Must Fix)
| # | File:Line | Issue | Recommendation |
|---|-----------|-------|----------------|
| 1 | [path:line] | [Issue description] | [How to fix] |

### 3.2 Major Issues (Should Fix)
| # | File:Line | Issue | Recommendation |
|---|-----------|-------|----------------|
| 1 | [path:line] | [Issue description] | [How to fix] |

### 3.3 Minor Issues (Nice to Fix)
| # | File:Line | Issue | Recommendation |
|---|-----------|-------|----------------|
| 1 | [path:line] | [Issue description] | [Suggestion] |

### 3.4 Positive Observations
- [Good practice observed]
- [Well-written code section]
- [Good test coverage area]

---

## 4. Discussion Points

| # | Topic | Question/Concern | Resolution |
|---|-------|------------------|------------|
| 1 | [Topic] | [Question] | [Resolution if discussed] |

---

## 5. Decision

### 5.1 Review Status
| Decision | Criteria |
|----------|----------|
| [ ] **Approved** | No critical/major issues, ready to merge |
| [ ] **Changes Requested** | Issues must be addressed before merge |
| [ ] **Needs Discussion** | Requires sync meeting to resolve concerns |

### 5.2 Conditions (if any)
- [ ] [Condition 1 - e.g., "Fix issue #1 before merge"]
- [ ] [Condition 2 - e.g., "Add test for edge case X"]

---

## 6. Follow-up

### 6.1 Re-review Required
| After Changes | Reviewer |
|---------------|----------|
| [ ] Yes [ ] No | [Name if yes] |

### 6.2 Technical Debt Created
| Item | Priority | Ticket |
|------|----------|--------|
| [Debt item] | [H/M/L] | [Link] |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial review |

---

*Template follows ISO/IEC 29110-5-1-2 Verification Results requirements.*
