# Design System

> Component library and design tokens for [PROJECT_NAME]

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[NAME]"
status: "Draft"
design_url: "[Figma/Storybook URL]"
```

---

## 1. Design Tokens

### 1.1 Spacing Scale
| Token | Value | CSS Variable | Usage |
|-------|-------|--------------|-------|
| `space-0` | 0px | `--space-0` | Reset |
| `space-1` | 4px | `--space-1` | Tight (icon padding) |
| `space-2` | 8px | `--space-2` | Related elements |
| `space-3` | 12px | `--space-3` | Compact spacing |
| `space-4` | 16px | `--space-4` | Standard (default) |
| `space-5` | 24px | `--space-5` | Section padding |
| `space-6` | 32px | `--space-6` | Card padding |
| `space-7` | 48px | `--space-7` | Section gaps |
| `space-8` | 64px | `--space-8` | Page sections |

### 1.2 Border Radius
| Token | Value | CSS Variable | Usage |
|-------|-------|--------------|-------|
| `radius-none` | 0px | `--radius-none` | Sharp corners |
| `radius-sm` | 4px | `--radius-sm` | Subtle rounding |
| `radius-md` | 8px | `--radius-md` | Buttons, inputs |
| `radius-lg` | 12px | `--radius-lg` | Cards |
| `radius-xl` | 16px | `--radius-xl` | Modals |
| `radius-full` | 9999px | `--radius-full` | Pills, avatars |

### 1.3 Shadows
| Token | Value | Usage |
|-------|-------|-------|
| `shadow-sm` | `0 1px 2px rgba(0,0,0,0.05)` | Subtle elevation |
| `shadow-md` | `0 4px 6px rgba(0,0,0,0.1)` | Cards |
| `shadow-lg` | `0 10px 15px rgba(0,0,0,0.1)` | Dropdowns |
| `shadow-xl` | `0 20px 25px rgba(0,0,0,0.15)` | Modals |

### 1.4 Z-Index Scale
| Token | Value | Usage |
|-------|-------|-------|
| `z-base` | 0 | Default |
| `z-dropdown` | 100 | Dropdowns, popovers |
| `z-sticky` | 200 | Sticky headers |
| `z-modal` | 300 | Modal overlays |
| `z-toast` | 400 | Toast notifications |
| `z-tooltip` | 500 | Tooltips |

---

## 2. Components

### 2.1 Button

**Variants:**
| Variant | Usage |
|---------|-------|
| Primary | Main CTA, one per screen |
| Secondary | Secondary actions |
| Tertiary/Ghost | Low emphasis actions |
| Destructive | Delete, remove actions |

**Sizes:**
| Size | Height | Padding | Font Size |
|------|--------|---------|-----------|
| Small | 32px | 12px 16px | 14px |
| Medium | 40px | 12px 20px | 16px |
| Large | 48px | 16px 24px | 18px |

**States:**
| State | Description |
|-------|-------------|
| Default | Normal appearance |
| Hover | Cursor over (desktop) |
| Active/Pressed | Being clicked |
| Focus | Keyboard focused |
| Disabled | Not interactive |
| Loading | Showing spinner |

### 2.2 Input

**Types:**
| Type | Usage |
|------|-------|
| Text | General text input |
| Password | Hidden text |
| Email | Email validation |
| Number | Numeric input |
| Search | Search with icon |
| Textarea | Multi-line text |

**States:**
| State | Visual Indicator |
|-------|------------------|
| Default | Gray border |
| Focus | Primary border, glow |
| Filled | Slightly darker background |
| Error | Red border, error message |
| Disabled | Grayed out, no interaction |
| Read-only | Visible but not editable |

**Anatomy:**
```
┌─────────────────────────────────────┐
│ Label                    (optional) │
├─────────────────────────────────────┤
│ [Icon] Placeholder text      [Icon] │
├─────────────────────────────────────┤
│ Helper text or error message        │
└─────────────────────────────────────┘
```

### 2.3 Card

**Variants:**
| Variant | Usage |
|---------|-------|
| Default | Standard content container |
| Elevated | Prominent cards with shadow |
| Outlined | Bordered, no shadow |
| Interactive | Clickable (hover state) |

**Anatomy:**
```
┌─────────────────────────────────────┐
│ [Image/Media]              optional │
├─────────────────────────────────────┤
│ Header                              │
│ Subheader                           │
├─────────────────────────────────────┤
│ Body content                        │
│ ...                                 │
├─────────────────────────────────────┤
│ [Actions]                  optional │
└─────────────────────────────────────┘
```

### 2.4 Modal/Dialog

**Types:**
| Type | Usage |
|------|-------|
| Alert | Important messages, requires acknowledgment |
| Confirm | Yes/No decisions |
| Form | Data input |
| Full-screen | Complex workflows (mobile) |

**Sizes:**
| Size | Max Width | Usage |
|------|-----------|-------|
| Small | 400px | Alerts, confirms |
| Medium | 560px | Forms |
| Large | 720px | Complex content |
| Full | 100% | Mobile full-screen |

### 2.5 Toast/Notification

**Types:**
| Type | Color | Icon | Duration |
|------|-------|------|----------|
| Success | Green | ✓ | 3s auto-dismiss |
| Error | Red | ✕ | Manual dismiss |
| Warning | Yellow | ⚠ | 5s auto-dismiss |
| Info | Blue | ℹ | 3s auto-dismiss |

**Position:** Top-right (desktop), Top-center (mobile)

### 2.6 Navigation

**Tab Bar (Mobile):**
| Attribute | Value |
|-----------|-------|
| Max Items | 5 |
| Height | 56px |
| Icon Size | 24px |
| Label | Optional, 12px |

**Sidebar (Desktop):**
| Attribute | Value |
|-----------|-------|
| Width (Expanded) | 240px |
| Width (Collapsed) | 64px |
| Item Height | 44px |

### 2.7 Table

**Features:**
| Feature | Support |
|---------|---------|
| Sorting | ✓ Column headers |
| Filtering | ✓ Per column or global |
| Pagination | ✓ 10/25/50 rows |
| Selection | ✓ Checkbox column |
| Actions | ✓ Row actions menu |

**Responsive:**
| Viewport | Behavior |
|----------|----------|
| Desktop | Full table |
| Tablet | Horizontal scroll |
| Mobile | Card view |

---

## 3. Patterns

### 3.1 Form Patterns

**Field Layout:**
```
Single column (mobile):
┌──────────────────┐
│ Field 1          │
├──────────────────┤
│ Field 2          │
├──────────────────┤
│ Field 3          │
└──────────────────┘

Two column (desktop):
┌─────────┬─────────┐
│ Field 1 │ Field 2 │
├─────────┴─────────┤
│ Field 3 (full)    │
└───────────────────┘
```

**Validation:**
| Timing | Behavior |
|--------|----------|
| On blur | Validate when leaving field |
| On submit | Validate all, focus first error |
| Real-time | For specific fields (password strength) |

### 3.2 Loading States

| Context | Pattern |
|---------|---------|
| Page load | Full-screen skeleton |
| Section load | Inline skeleton |
| Button action | Spinner in button |
| Data fetch | Skeleton rows/cards |
| Infinite scroll | Spinner at bottom |

### 3.3 Empty States

**Structure:**
```
┌─────────────────────────────────┐
│        [Illustration]          │
│                                 │
│     Primary message (H3)        │
│  Secondary message (body text)  │
│                                 │
│       [CTA Button]              │
└─────────────────────────────────┘
```

### 3.4 Error States

| Type | Display |
|------|---------|
| Field error | Inline below field |
| Form error | Banner above form |
| Page error | Full error page |
| Network error | Toast + retry |

---

## 4. Animation

### 4.1 Duration
| Token | Duration | Usage |
|-------|----------|-------|
| `duration-fast` | 100ms | Micro-interactions (hover) |
| `duration-normal` | 200ms | Standard transitions |
| `duration-slow` | 300ms | Modal/drawer enter |
| `duration-slower` | 500ms | Page transitions |

### 4.2 Easing
| Token | Value | Usage |
|-------|-------|-------|
| `ease-in` | cubic-bezier(0.4, 0, 1, 1) | Exit animations |
| `ease-out` | cubic-bezier(0, 0, 0.2, 1) | Enter animations |
| `ease-in-out` | cubic-bezier(0.4, 0, 0.2, 1) | Standard |

---

## 5. Implementation

### 5.1 CSS Variables
```css
:root {
  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  /* ... */

  /* Colors (from branding) */
  --color-primary: #XXXXXX;
  /* ... */

  /* Radius */
  --radius-md: 8px;
  /* ... */
}
```

### 5.2 Component Library
| Platform | Library |
|----------|---------|
| Web (React) | [Custom / shadcn/ui / Chakra] |
| Mobile (React Native) | [Custom / NativeBase] |
| Mobile (Flutter) | [Custom / Material] |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial system |

---

*Design System complements ISO/IEC 29110-5-1-2 Software Design.*
