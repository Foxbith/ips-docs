# Screen: [SCREEN_NAME]

> Screen specification for [PROJECT_NAME]

---

## Metadata

```yaml
id: SCR-[XXX]
project: "[PROJECT_NAME]"
screen_name: "[Screen Name]"
version: "1.0"
created: "YYYY-MM-DD"
author: "[NAME]"
status: "Draft"
figma_url: "[Figma frame URL]"
```

---

## 1. Overview

| Attribute | Value |
|-----------|-------|
| **Screen Name** | [Name] |
| **Route/URL** | `/[path]` |
| **Platform** | [Web / iOS / Android / All] |
| **User Role** | [Who can access] |
| **Requirements** | FR-XXX, FR-YYY |

---

## 2. Purpose

[1-2 sentences describing what users accomplish on this screen]

---

## 3. Entry & Exit Points

### 3.1 Entry Points (How users arrive)
| From | Action | Condition |
|------|--------|-----------|
| [Previous screen] | [Button/Link click] | [Any conditions] |
| [Navigation] | [Tab/menu selection] | - |
| [Direct URL] | `/[path]` | [If allowed] |

### 3.2 Exit Points (Where users go next)
| To | Action | Condition |
|----|--------|-----------|
| [Next screen] | [Button click] | [Success] |
| [Previous screen] | [Back button] | - |
| [Error screen] | [System] | [On error] |

---

## 4. Layout

### 4.1 Wireframe (Text Description for AI)

```
┌─────────────────────────────────────────┐
│ [Header]                                │
│ ← Back    Page Title           [Action] │
├─────────────────────────────────────────┤
│                                         │
│ [Section 1]                             │
│ ┌─────────────────────────────────────┐ │
│ │ Content area description            │ │
│ │ - Element 1                         │ │
│ │ - Element 2                         │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ [Section 2]                             │
│ ┌─────────────────────────────────────┐ │
│ │ Content area description            │ │
│ └─────────────────────────────────────┘ │
│                                         │
├─────────────────────────────────────────┤
│ [Footer / CTA Button]                   │
└─────────────────────────────────────────┘
```

### 4.2 Wireframe Image
**File:** `./wireframes/SCR-[XXX]-[name].png`
**Figma:** [Link to specific frame]

---

## 5. Components

### 5.1 Header
| Element | Type | Content | Action |
|---------|------|---------|--------|
| Back Button | Icon Button | ← | Navigate back |
| Title | Text | [Page Title] | - |
| Action | Icon/Button | [Action name] | [Action] |

### 5.2 Content Area
| Element | Type | Content | Interaction |
|---------|------|---------|-------------|
| [Element 1] | [Component type] | [Content/data] | [On tap/click] |
| [Element 2] | [Component type] | [Content/data] | [On tap/click] |

### 5.3 Footer/Actions
| Element | Type | Label | Action |
|---------|------|-------|--------|
| Primary CTA | Button Primary | [Label] | [Action] |
| Secondary | Button Secondary | [Label] | [Action] |

---

## 6. States

### 6.1 Default State
**Description:** [Normal view when data is present]
**Visual:** [Reference to wireframe/Figma]

### 6.2 Loading State
**Description:** [What shows while loading]
**Elements:**
- Skeleton loaders for [X, Y, Z]
- Spinner for [specific action]

### 6.3 Empty State
**Description:** [When no data exists]
**Content:**
- Illustration: [Description]
- Title: "[Empty state title]"
- Message: "[Helpful message]"
- CTA: [Button to create/add]

### 6.4 Error State
**Description:** [When something goes wrong]
**Content:**
- Icon/Illustration: [Error indicator]
- Title: "[Error title]"
- Message: "[Error description]"
- CTA: [Retry button]

### 6.5 Success State (if applicable)
**Description:** [After successful action]
**Feedback:** [Toast/Modal/Redirect]

---

## 7. Interactions

### 7.1 Gestures (Mobile)
| Gesture | Element | Action |
|---------|---------|--------|
| Tap | [Element] | [Action] |
| Long press | [Element] | [Action] |
| Swipe left | [Element] | [Action] |
| Pull to refresh | Screen | Reload data |

### 7.2 Animations
| Trigger | Animation | Duration |
|---------|-----------|----------|
| Page enter | Fade in | 200ms |
| [Element] appear | Slide up | 300ms |
| Loading | Pulse/Skeleton | Continuous |

---

## 8. Data

### 8.1 Data Sources
| Data | Source | Refresh |
|------|--------|---------|
| [Data 1] | API: `/endpoint` | On load |
| [Data 2] | Local storage | Cached |

### 8.2 Form Inputs (if applicable)
| Field | Type | Validation | Required |
|-------|------|------------|----------|
| [Field 1] | Text | [Rules] | Yes/No |
| [Field 2] | Email | Valid email | Yes |
| [Field 3] | Select | [Options] | Yes |

---

## 9. Responsive Behavior

| Breakpoint | Changes |
|------------|---------|
| Mobile (< 576px) | [Layout changes] |
| Tablet (576-1023px) | [Layout changes] |
| Desktop (1024px+) | [Layout changes] |

---

## 10. Accessibility

| Requirement | Implementation |
|-------------|----------------|
| Screen reader | [Heading hierarchy, labels] |
| Keyboard nav | [Tab order: X → Y → Z] |
| Focus | [Focus trap in modal] |
| Contrast | [Verified against AA] |

---

## 11. Related Artifacts

| Type | ID | Description |
|------|-----|-------------|
| Requirement | FR-XXX | [Requirement title] |
| User Flow | UF-XXX | [Flow this screen is part of] |
| Test Case | TC-XXX | [Test for this screen] |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial specification |

---

*Template follows ISO/IEC 29110-5-1-2 Software Design requirements.*
