# ISO 29110 Documentation Templates

> Centralized ISO/IEC 29110-5-1-2 Basic Profile templates for Foxbith projects

## Overview

This directory contains standardized documentation templates that comply with **ISO/IEC 29110-5-1-2** (Software Engineering for Very Small Entities - Basic Profile).

### Key Features
- **Single Source of Truth** - All templates maintained here
- **Human + AI Readable** - Structured for both human editing and AI generation
- **Phase-Aware** - Supports multi-phase projects with separate contracts
- **Consistent Metadata** - YAML frontmatter for AI parsing

---

## Quick Start

### For New Projects

```bash
# Copy templates to your project
cp -r 02-declared-intent/templates/iso-29110/* your-project-docs/

# Replace placeholders
find your-project-docs/ -name "*.md" -exec sed -i '' 's/\[PROJECT_NAME\]/YourProject/g' {} \;
```

### Creating New Documents

**From Templates (Iteration/Split files):**
```bash
# Copy _template.md and rename with proper ID/date
cp 02-requirements/specifications/functional-requirements/_template.md \
   02-requirements/specifications/functional-requirements/FR-001-user-login.md
```

---

## File Type Classification

| Symbol | Type | Description | Naming Pattern |
|--------|------|-------------|----------------|
| 📄 | Single | One per project, updated over time | `{name}.md` |
| 📅 | Iteration | One per occurrence (dated/versioned) | `sprint-29Nov2025.md` |
| 📂 | Split | One per item with ID prefix | `FR-001-{name}.md` |

---

## Folder Structure

```
iso-29110/
├── 00-assets/                            # Project Assets
│   ├── images/                           # Screenshots, logos, mockups
│   ├── documents/                        # PDFs, spreadsheets, external docs
│   ├── diagrams/                         # Source files (draw.io, Excalidraw)
│   └── README.md                         # 📄 Asset guidelines
│
├── 01-planning/                          # Project Planning
│   ├── contracts/
│   │   └── _template.md                  # 📅 SOW-phase{N}-{DATE}.md
│   ├── project-plans/
│   │   └── _template.md                  # 📅 plan-phase{N}-{NAME}.md
│   ├── meeting-record/
│   │   └── _template.md                  # 📅 YYYY-MM-DD.md
│   ├── progress-tracking/
│   │   └── _template.md                  # 📅 sprint-{DATE}.md
│   ├── change-requests/
│   │   └── _template.md                  # 📂 CR-{XXX}-{name}.md
│   ├── scope-definitions/
│   │   └── _template.md                  # 📅 scope-phase{N}-{TYPE}.md
│   ├── raci-matrix.md                    # 📄 Responsibility matrix
│   └── correction-register.md            # 📄 Issue tracking
│
├── 02-requirements/                      # Requirements Analysis
│   ├── specifications/
│   │   ├── functional-requirements/
│   │   │   └── _template.md              # 📂 FR-{XXX}-{name}.md
│   │   ├── interface-requirements/
│   │   │   └── _template.md              # 📂 INT-{XXX}-{name}.md
│   │   └── non-functional-requirements/
│   │       └── _template.md              # 📂 NFR-{XXX}-{name}.md
│   └── traceability-matrix.md            # 📄 Requirements tracing
│
├── 03-design/                            # Software Design
│   ├── software-design/
│   │   ├── 01-system-context.md          # 📄 C4 Level 1
│   │   ├── 02-container-architecture.md  # 📄 C4 Level 2
│   │   ├── design-decisions/
│   │   │   └── _template.md              # 📂 ADR-{XXX}-{name}.md
│   │   └── api-design/
│   │       └── _template.yaml            # 📂 {service}-api.yaml
│   ├── ux-ui-design/
│   │   ├── 01-design-overview.md         # 📄 Single file
│   │   ├── 02-branding-guidelines.md     # 📄 Single file (CI/brand)
│   │   ├── 03-design-system.md           # 📄 Single file (tokens/components)
│   │   ├── 04-information-architecture.md # 📄 Single file (sitemap/nav)
│   │   ├── 05-accessibility.md           # 📄 Single file (WCAG)
│   │   ├── personas/
│   │   │   └── _template.md              # 📂 PER-{XXX}-{name}.md
│   │   ├── screens/
│   │   │   └── _template.md              # 📂 SCR-{XXX}-{name}.md
│   │   └── user-flows/
│   │       └── _template.md              # 📂 UF-{XXX}-{name}.md
│   └── infrastructure/                   # SA/DevOps planning
│       ├── 01-repository-structure.md    # 📄 Repos, branching, access
│       ├── 02-secrets-management.md      # 📄 Secrets, env vars, rotation
│       ├── 03-ci-cd-pipelines.md         # 📄 GitHub Actions, deployment
│       └── 04-developer-onboarding.md    # 📄 Setup, access, tooling
│
├── 04-development/                       # Development
│   ├── coding-standards.md               # 📄 Code conventions
│   ├── code-review/
│   │   └── _template.md                  # 📅 review-{DATE}-{name}.md
│   └── verification/
│       └── _template.md                  # 📅 verification-v{VERSION}.md
│
├── 05-quality/                           # Quality Assurance
│   ├── test-plan.md                      # 📄 Test strategy
│   ├── test-cases/
│   │   └── _template.md                  # 📂 TC-{XXX}-{name}.md
│   ├── test-reports/
│   │   └── _template.md                  # 📅 test-report-v{VERSION}.md
│   └── validation/
│       └── _template.md                  # 📅 validation-v{VERSION}.md
│
├── 06-support/                           # Delivery & Support
│   ├── operation-guide.md                # 📄 Operations runbook
│   ├── maintenance-guide.md              # 📄 Maintenance procedures
│   ├── acceptance/
│   │   └── _template.md                  # 📅 acceptance-{MILESTONE}.md
│   ├── delivery/
│   │   └── _template.md                  # 📅 delivery-v{VERSION}.md
│   └── release-notes/
│       └── _template.md                  # 📅 v{VERSION}.md
│
├── README.md                             # This file
└── version.json                          # Template metadata
```

---

## Multi-Phase Project Support

Templates support projects with multiple phases/contracts:

```
01-planning/
├── contracts/
│   ├── _template.md
│   ├── SOW-phase1-29Nov2025.md           # Phase 1 contract
│   └── SOW-phase2-15Mar2026.md           # Phase 2 contract
├── project-plans/
│   ├── _template.md
│   ├── plan-phase1-mvp.md                # Phase 1 plan
│   └── plan-phase2-scale.md              # Phase 2 plan
```

Requirements span phases via metadata:
```yaml
# In FR-051-dashboard.md
---
id: FR-051
phase: 2                    # Added in Phase 2
contract_ref: "SOW-phase2"  # Links to contract
---
```

---

## AI Integration

### Template Structure for AI
All templates include:
- **YAML Metadata** - Structured frontmatter for parsing
- **Consistent Sections** - Predictable structure
- **Placeholder Variables** - `[PROJECT_NAME]`, `[X.Y.Z]`, `YYYY-MM-DD`

### AI Workflow
```
1. AI reads: _template.md
2. AI generates: FR-051-new-feature.md (with filled content)
3. Human reviews and approves
4. Git tracks changes
```

### Common Placeholders
| Placeholder | Description | Example |
|-------------|-------------|---------|
| `[PROJECT_NAME]` | Project name | "Retouch Platform" |
| `[CLIENT_NAME]` | Client name | "Innotech Venture" |
| `[N]` | Phase number | 1, 2, 3 |
| `[XXX]` | ID number | 001, 052, 100 |
| `YYYY-MM-DD` | ISO date | 2025-11-29 |
| `[X.Y.Z]` | Semantic version | 1.2.3 |

---

## Template Sync (Planned)

GitHub Actions will sync templates to project repos:

```
zoo-strategy (this repo)              Target Repos
┌─────────────────────────┐           ┌──────────────────┐
│ templates/iso-29110/    │  ──────►  │ retouch-docs/    │
│                         │   Auto    │ bumpcall-docs/   │
│                         │    PR     │ whalevox-docs/   │
└─────────────────────────┘           └──────────────────┘
```

---

## Contributing

### Proposing Changes
1. Create issue describing the change
2. Reference ISO 29110 work product (WP##)
3. Submit PR with template updates
4. Update version.json

### Template Quality Checklist
- [ ] YAML metadata included
- [ ] All placeholders use consistent format
- [ ] Document control section present
- [ ] Tables properly formatted
- [ ] No project-specific content

---

## References

- [ISO/IEC 29110](https://www.iso.org/standard/62711.html)
- [ISO 29110 Deployment Packages](http://profs.etsmtl.ca/clalonde/English/VSE/index.html)
- [Foxbith innotech-docs](https://github.com/Foxbith/innotech-docs) - Reference implementation

---

## Version

Current Version: **1.0.0** (2025-11-29)

See `version.json` for template metadata.

---

*Templates follow ISO/IEC 29110-5-1-2 Basic Profile for Very Small Entities (VSEs).*
