# NFR-[XXX]: [Requirement Title]

> ISO/IEC 29110-5-1-2 Work Product: Requirements Specification - Non-Functional

---

## Metadata

```yaml
id: NFR-[XXX]
title: "[Requirement Title]"
category: "Non-Functional"
subcategory: "[Performance/Security/Availability/Usability/Maintainability/Scalability]"
phase: [N]
contract_ref: "SOW-phase[N]-[DATE]"
version: "1.0"
status: "Draft"
priority: "[Must Have/Should Have/Could Have/Won't Have]"
created: "YYYY-MM-DD"
last_modified: "YYYY-MM-DD"
author: "[NAME]"
approved_by: "[PENDING]"
```

---

## Requirement Statement

**As a** [stakeholder / system user / operator]
**I want** [quality attribute / constraint]
**So that** [business benefit / risk mitigation]

---

## Detailed Description

[2-4 sentences describing the non-functional requirement. What quality attribute is being specified? Why is it important?]

---

## Specification

### Target Metrics

| Metric | Target | Minimum Acceptable | Measurement Method |
|--------|--------|-------------------|-------------------|
| [Metric 1] | [Target value] | [Minimum value] | [How to measure] |
| [Metric 2] | [Target value] | [Minimum value] | [How to measure] |

### Conditions
| Condition | Value |
|-----------|-------|
| **Environment** | [Production / Staging / All] |
| **Load** | [Normal / Peak / Stress] |
| **Time Window** | [24/7 / Business hours] |
| **Exclusions** | [Planned maintenance / etc.] |

---

## Category-Specific Details

### Performance (if applicable)
| Aspect | Requirement |
|--------|-------------|
| Response Time (avg) | [X] ms |
| Response Time (p95) | [X] ms |
| Response Time (p99) | [X] ms |
| Throughput | [X] requests/second |
| Concurrent Users | [X] users |

### Availability (if applicable)
| Aspect | Requirement |
|--------|-------------|
| Uptime SLA | [X]% |
| Allowed Downtime | [X] hours/month |
| MTTR (Mean Time to Recovery) | [X] minutes |
| RTO (Recovery Time Objective) | [X] hours |
| RPO (Recovery Point Objective) | [X] hours |

### Security (if applicable)
| Aspect | Requirement |
|--------|-------------|
| Authentication | [Method] |
| Authorization | [RBAC/ABAC/etc.] |
| Encryption in Transit | [TLS 1.2+] |
| Encryption at Rest | [AES-256] |
| Compliance | [GDPR/HIPAA/PDPA/etc.] |

### Scalability (if applicable)
| Aspect | Requirement |
|--------|-------------|
| Horizontal Scaling | [Auto/Manual] |
| Max Instances | [X] |
| Data Growth | [X] GB/month |
| User Growth | [X] users/month |

### Usability (if applicable)
| Aspect | Requirement |
|--------|-------------|
| Accessibility | [WCAG 2.1 Level AA] |
| Language Support | [Languages] |
| Mobile Responsive | [Yes/No] |
| Offline Capability | [Yes/No] |

### Maintainability (if applicable)
| Aspect | Requirement |
|--------|-------------|
| Code Coverage | [X]% |
| Documentation | [Required level] |
| Deployment Frequency | [X per week] |
| Mean Time to Deploy | [X] minutes |

---

## Acceptance Criteria

- [ ] [Measurable criterion 1]
- [ ] [Measurable criterion 2]
- [ ] [Testable condition]
- [ ] [Verification method defined]

---

## Verification Method

| Method | Description | Frequency |
|--------|-------------|-----------|
| **Testing** | [Performance/Load/Security test] | [Per release] |
| **Monitoring** | [Real-time metrics] | [Continuous] |
| **Audit** | [Periodic review] | [Quarterly] |
| **Tools** | [Specific tools used] | |

---

## Dependencies

- [NFR-XXX] - [Related quality requirement]
- [FR-XXX] - [Feature that must meet this NFR]
- [Infrastructure] - [Required infrastructure]

---

## Traceability

| Artifact Type | Reference | Notes |
|---------------|-----------|-------|
| Contract | SOW-phase[N] | Section on SLAs |
| Design | [Architecture component] | |
| Test Plan | [Performance test section] | |

---

## References

- **Planning Document:** `01-planning/contracts/SOW-phase[N]-[DATE].md`
- **Industry Standard:** [ISO/OWASP/etc. if applicable]
- **Related NFR:** NFR-XXX, NFR-YYY

---

## Notes

**Assumptions:**
- [Infrastructure supports required performance]
- [Third-party services meet their SLAs]

**Trade-offs:**
- [Performance vs. cost considerations]
- [Security vs. usability balance]

**Monitoring:**
- [How this NFR will be monitored in production]
- [Alert thresholds]

---

## Change History

| Version | Date | Author | Description | Approved By |
|---------|------|--------|-------------|-------------|
| 1.0 | YYYY-MM-DD | [Name] | Initial requirement | [Pending] |

---

*Template follows ISO/IEC 29110-5-1-2 Requirements Specification format.*
