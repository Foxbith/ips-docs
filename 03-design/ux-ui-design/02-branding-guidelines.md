# Branding Guidelines

> Corporate Identity (CI) and Brand Standards for [PROJECT_NAME]

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
client: "[CLIENT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[NAME]"
status: "Draft"
```

---

## 1. Brand Overview

### 1.1 Brand Mission
[One sentence describing the brand's purpose]

### 1.2 Brand Vision
[One sentence describing where the brand is heading]

### 1.3 Brand Values
| Value | Description |
|-------|-------------|
| [Value 1] | [How this manifests in the product] |
| [Value 2] | [How this manifests in the product] |
| [Value 3] | [How this manifests in the product] |

---

## 2. Logo

### 2.1 Primary Logo
| Attribute | Value |
|-----------|-------|
| **File Location** | `assets/logo/` |
| **Formats** | SVG (primary), PNG (@1x, @2x, @3x) |
| **Minimum Size** | [X]px width |
| **Clear Space** | [X]px around logo |

### 2.2 Logo Variants
| Variant | Usage | File |
|---------|-------|------|
| Full Color | Default usage | `logo-color.svg` |
| White/Reversed | Dark backgrounds | `logo-white.svg` |
| Black/Monochrome | Print, low color | `logo-black.svg` |
| Icon Only | Favicon, app icon | `logo-icon.svg` |

### 2.3 Logo Don'ts
- ❌ Do not stretch or distort
- ❌ Do not change colors
- ❌ Do not add effects (shadow, glow)
- ❌ Do not place on busy backgrounds
- ❌ Do not rotate

---

## 3. Color Palette

### 3.1 Primary Colors
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Primary | #[XXXXXX] | rgb(X, X, X) | Main brand color, CTAs |
| Primary Dark | #[XXXXXX] | rgb(X, X, X) | Hover states |
| Primary Light | #[XXXXXX] | rgb(X, X, X) | Backgrounds, accents |

### 3.2 Secondary Colors
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Secondary | #[XXXXXX] | rgb(X, X, X) | Secondary actions |
| Accent | #[XXXXXX] | rgb(X, X, X) | Highlights |

### 3.3 Neutral Colors
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Black | #[XXXXXX] | rgb(X, X, X) | Headings |
| Gray 900 | #[XXXXXX] | rgb(X, X, X) | Body text |
| Gray 600 | #[XXXXXX] | rgb(X, X, X) | Secondary text |
| Gray 300 | #[XXXXXX] | rgb(X, X, X) | Borders |
| Gray 100 | #[XXXXXX] | rgb(X, X, X) | Backgrounds |
| White | #FFFFFF | rgb(255, 255, 255) | Cards, surfaces |

### 3.4 Semantic Colors
| Name | Hex | Usage |
|------|-----|-------|
| Success | #[XXXXXX] | Success messages, confirmations |
| Warning | #[XXXXXX] | Warning messages, cautions |
| Error | #[XXXXXX] | Error messages, destructive actions |
| Info | #[XXXXXX] | Informational messages |

---

## 4. Typography

### 4.1 Font Families
| Type | Font Name | Fallback | License |
|------|-----------|----------|---------|
| Primary (Headings) | [Font Name] | [Sans-serif] | [Google Fonts / Commercial] |
| Secondary (Body) | [Font Name] | [Sans-serif] | [Google Fonts / Commercial] |
| Monospace (Code) | [Font Name] | [Monospace] | [Google Fonts / Commercial] |

### 4.2 Font Files
| Font | Weights | Location |
|------|---------|----------|
| [Primary Font] | 400, 500, 600, 700 | `assets/fonts/` |
| [Secondary Font] | 400, 500 | `assets/fonts/` |

### 4.3 Type Scale
| Style | Font | Size | Weight | Line Height | Letter Spacing |
|-------|------|------|--------|-------------|----------------|
| Display | Primary | 48px | 700 | 1.2 | -0.02em |
| H1 | Primary | 32px | 700 | 1.3 | -0.01em |
| H2 | Primary | 24px | 600 | 1.3 | 0 |
| H3 | Primary | 20px | 600 | 1.4 | 0 |
| Body Large | Secondary | 18px | 400 | 1.6 | 0 |
| Body | Secondary | 16px | 400 | 1.6 | 0 |
| Body Small | Secondary | 14px | 400 | 1.5 | 0 |
| Caption | Secondary | 12px | 400 | 1.4 | 0.01em |

---

## 5. Brand Voice

### 5.1 Tone Attributes
| Attribute | Description | Example |
|-----------|-------------|---------|
| [Friendly] | [Warm, approachable] | "Great job! You're all set." |
| [Professional] | [Clear, competent] | "Your request has been processed." |
| [Helpful] | [Supportive, guiding] | "Need help? We're here for you." |

### 5.2 Writing Guidelines
| Do | Don't |
|----|-------|
| Use active voice | Use passive voice |
| Be concise | Be verbose |
| Use simple words | Use jargon |
| Be positive | Be negative |

### 5.3 UI Copy Examples
| Context | Good | Bad |
|---------|------|-----|
| Error | "Couldn't save. Please try again." | "Error 500: Internal server error" |
| Success | "Saved!" | "Operation completed successfully" |
| Empty State | "No orders yet. Ready to shop?" | "No data available" |
| Button | "Get Started" | "Submit" |

---

## 6. Imagery

### 6.1 Photography Style
| Attribute | Guideline |
|-----------|-----------|
| Style | [Natural, candid / Studio, polished] |
| Lighting | [Bright, airy / Moody, dramatic] |
| Subjects | [People, products, lifestyle] |
| Color Treatment | [Warm tones / Cool tones / Vibrant] |

### 6.2 Illustration Style
| Attribute | Guideline |
|-----------|-----------|
| Style | [Flat, minimalist / 3D, detailed] |
| Line Weight | [Thin / Bold] |
| Colors | [Brand colors only / Extended palette] |

### 6.3 Iconography
| Attribute | Value |
|-----------|-------|
| Style | [Outline / Filled / Duotone] |
| Stroke Width | [1.5px / 2px] |
| Corner Radius | [Rounded / Square] |
| Icon Library | [Custom / Heroicons / Lucide] |

---

## 7. Brand Assets

### 7.1 Asset Locations
| Asset Type | Location | Formats |
|------------|----------|---------|
| Logos | `assets/logo/` | SVG, PNG |
| Icons | `assets/icons/` | SVG |
| Fonts | `assets/fonts/` | WOFF2, TTF |
| Illustrations | `assets/illustrations/` | SVG, PNG |
| Photos | `assets/photos/` | JPG, WebP |

### 7.2 Asset Naming Convention
```
{type}-{name}-{variant}.{format}
Examples:
- logo-primary-color.svg
- icon-arrow-right.svg
- illustration-empty-state.svg
```

---

## 8. Application Examples

### 8.1 Digital Applications
- Website
- Mobile App
- Email Templates
- Social Media

### 8.2 Print Applications (if applicable)
- Business Cards
- Letterhead
- Marketing Materials

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial guidelines |

---

*Branding guidelines complement ISO/IEC 29110-5-1-2 Software Design.*
