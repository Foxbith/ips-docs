# Requirements Traceability Matrix

> ISO/IEC 29110-5-1-2 Work Product: Traceability Record

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
maintained_by: "[NAME]"
```

---

## Purpose

This matrix traces requirements through design, implementation, and testing to ensure complete coverage and facilitate impact analysis for changes.

---

## 1. Requirements to Design Traceability

| Req ID | Requirement Title | Design Component | Design Document | Status |
|--------|-------------------|------------------|-----------------|--------|
| FR-001 | [Title] | [Component name] | `03-design/software-design/03-component-design.md` | [Designed/Pending] |
| FR-002 | [Title] | [Component name] | `03-design/software-design/03-component-design.md` | [Designed/Pending] |
| INT-001 | [Title] | [API/Integration] | `03-design/software-design/api-design/[name].yaml` | [Designed/Pending] |
| NFR-001 | [Title] | [Architecture aspect] | `03-design/software-design/04-deployment-architecture.md` | [Designed/Pending] |

---

## 2. Requirements to Test Cases Traceability

| Req ID | Requirement Title | Test Case(s) | Test Type | Coverage |
|--------|-------------------|--------------|-----------|----------|
| FR-001 | [Title] | TC-001, TC-002 | Unit, E2E | [Complete/Partial] |
| FR-002 | [Title] | TC-003 | Integration | [Complete/Partial] |
| INT-001 | [Title] | TC-010, TC-011 | Integration | [Complete/Partial] |
| NFR-001 | [Title] | PERF-001 | Performance | [Complete/Partial] |

---

## 3. Requirements to Source Code Traceability

| Req ID | Requirement Title | Module/Component | File(s) | Status |
|--------|-------------------|------------------|---------|--------|
| FR-001 | [Title] | [Module] | `src/modules/[name]` | [Implemented/In Progress] |
| FR-002 | [Title] | [Module] | `src/modules/[name]` | [Implemented/In Progress] |

---

## 4. Test Cases to Requirements (Reverse Traceability)

| Test ID | Test Title | Requirements Covered | Result |
|---------|------------|---------------------|--------|
| TC-001 | [Title] | FR-001 | [Pass/Fail/Not Run] |
| TC-002 | [Title] | FR-001, FR-005 | [Pass/Fail/Not Run] |
| TC-003 | [Title] | FR-002, NFR-003 | [Pass/Fail/Not Run] |

---

## 5. Coverage Summary

### By Phase
| Phase | Total Reqs | Designed | Implemented | Tested | Validated |
|-------|------------|----------|-------------|--------|-----------|
| Phase 1 | [X] | [X] | [X] | [X] | [X] |
| Phase 2 | [X] | [X] | [X] | [X] | [X] |

### By Category
| Category | Total | Designed | Implemented | Tested | Coverage % |
|----------|-------|----------|-------------|--------|------------|
| Functional (FR) | [X] | [X] | [X] | [X] | [X]% |
| Interface (INT) | [X] | [X] | [X] | [X] | [X]% |
| Non-Functional (NFR) | [X] | [X] | [X] | [X] | [X]% |
| **Total** | **[X]** | **[X]** | **[X]** | **[X]** | **[X]%** |

### Gaps
| Gap Type | Count | Details |
|----------|-------|---------|
| Requirements without tests | [X] | [List: FR-XXX, FR-YYY] |
| Requirements without design | [X] | [List] |
| Tests without requirements | [X] | [List: TC-XXX] |

---

## 6. Impact Analysis Log

When a requirement changes, use this section to track impact:

| Change ID | Changed Req | Affected Design | Affected Tests | Affected Code | Impact Level |
|-----------|-------------|-----------------|----------------|---------------|--------------|
| CR-001 | FR-005 | Component X | TC-010, TC-011 | `src/auth/*` | High |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial matrix |

---

*Matrix follows ISO/IEC 29110-5-1-2 Traceability Record requirements.*
