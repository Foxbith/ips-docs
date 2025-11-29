# Project Assets

> Centralized storage for project images, documents, and diagrams

---

## Structure

```
00-assets/
├── images/           # Screenshots, logos, photos
├── documents/        # PDFs, spreadsheets, external docs
├── diagrams/         # Source files for diagrams (draw.io, Mermaid)
└── README.md         # This file
```

## Usage Guidelines

### Images (`images/`)

| Type | Naming Convention | Example |
|------|-------------------|---------|
| Screenshots | `{feature}-{description}.png` | `login-form-validation.png` |
| Logos | `logo-{variant}.{ext}` | `logo-dark.svg` |
| UI Mockups | `{screen}-{version}.png` | `dashboard-v2.png` |
| Icons | `icon-{name}.svg` | `icon-notification.svg` |

**Best practices:**
- Use PNG for screenshots, SVG for icons/logos
- Optimize images before committing (use tinypng.com or similar)
- Maximum file size: 1MB per image
- Use descriptive names (avoid `screenshot1.png`)

### Documents (`documents/`)

| Type | Naming Convention | Example |
|------|-------------------|---------|
| Client docs | `{date}-{type}-{name}.pdf` | `2025-01-15-contract-signed.pdf` |
| Research | `research-{topic}.pdf` | `research-competitor-analysis.pdf` |
| Exports | `export-{source}-{date}.xlsx` | `export-analytics-2025-01.xlsx` |

**Best practices:**
- Include date prefix for versioned documents
- Keep original source files when possible
- Add to `.gitignore` if file is too large (>10MB)

### Diagrams (`diagrams/`)

| Type | Naming Convention | Example |
|------|-------------------|---------|
| Architecture | `arch-{component}.drawio` | `arch-system-context.drawio` |
| Flows | `flow-{process}.drawio` | `flow-checkout.drawio` |
| ERD | `erd-{schema}.drawio` | `erd-main-database.drawio` |

**Best practices:**
- Store source files (.drawio, .excalidraw) here
- Export PNG/SVG to `images/` for documentation use
- Use Mermaid in markdown when possible (no source file needed)

---

## Referencing Assets

### In Markdown Files

```markdown
<!-- Relative path from document location -->
![Login Flow](../00-assets/images/login-flow.png)

<!-- From any location -->
![Logo](../../00-assets/images/logo-dark.svg)
```

### In Design Documents

Reference assets in `03-design/` documents:
```markdown
## UI Mockups

See: [Dashboard Mockup](../00-assets/images/dashboard-v2.png)
```

---

## Git LFS (Optional)

For large files, consider using Git LFS:

```bash
# Install Git LFS
git lfs install

# Track large file types
git lfs track "*.psd"
git lfs track "*.sketch"
git lfs track "*.fig"

# Commit .gitattributes
git add .gitattributes
```

---

*Asset management for ISO/IEC 29110-5-1-2 compliance.*
