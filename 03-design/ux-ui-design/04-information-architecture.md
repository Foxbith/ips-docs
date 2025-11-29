# Information Architecture

> Sitemap, navigation structure, and content organization for [PROJECT_NAME]

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[NAME]"
status: "Draft"
```

---

## 1. Sitemap

### 1.1 Application Structure

```
[PROJECT_NAME]
│
├── 🔓 Public (Unauthenticated)
│   ├── Landing Page
│   ├── Login
│   ├── Register
│   ├── Forgot Password
│   └── Reset Password
│
├── 🔐 Authenticated
│   ├── Dashboard / Home
│   │   ├── Overview
│   │   ├── Quick Actions
│   │   └── Recent Activity
│   │
│   ├── [Feature Area 1]
│   │   ├── List View
│   │   ├── Detail View (/:id)
│   │   ├── Create
│   │   └── Edit (/:id/edit)
│   │
│   ├── [Feature Area 2]
│   │   └── ...
│   │
│   ├── Profile
│   │   ├── Account Settings
│   │   ├── Preferences
│   │   ├── Notifications
│   │   └── Security
│   │
│   └── Settings (Admin)
│       ├── Team Management
│       ├── Billing
│       └── Integrations
│
└── 📄 Static Pages
    ├── Help / FAQ
    ├── Privacy Policy
    ├── Terms of Service
    └── Contact
```

### 1.2 URL Structure

| Page | URL Pattern | Example |
|------|-------------|---------|
| Dashboard | `/` or `/dashboard` | `/dashboard` |
| Feature List | `/[feature]` | `/orders` |
| Feature Detail | `/[feature]/:id` | `/orders/123` |
| Feature Create | `/[feature]/new` | `/orders/new` |
| Feature Edit | `/[feature]/:id/edit` | `/orders/123/edit` |
| Profile | `/profile` | `/profile` |
| Settings | `/settings` | `/settings` |

---

## 2. Navigation Structure

### 2.1 Primary Navigation

| Platform | Type | Location |
|----------|------|----------|
| Mobile | Bottom Tab Bar | Fixed bottom |
| Desktop | Sidebar | Fixed left |

**Primary Nav Items:**
| Order | Label | Icon | Route | Badge |
|-------|-------|------|-------|-------|
| 1 | Home | 🏠 | `/dashboard` | - |
| 2 | [Feature 1] | [icon] | `/[feature1]` | Count |
| 3 | [Feature 2] | [icon] | `/[feature2]` | - |
| 4 | [Feature 3] | [icon] | `/[feature3]` | - |
| 5 | Profile | 👤 | `/profile` | - |

### 2.2 Secondary Navigation

**Location:** Inside primary nav sections or tabs within pages

| Parent | Sub-items |
|--------|-----------|
| Dashboard | Overview, Activity, Analytics |
| Profile | Account, Preferences, Security |
| Settings | Team, Billing, Integrations |

### 2.3 Utility Navigation

**Location:** Header (desktop) or hamburger menu (mobile)

| Item | Action |
|------|--------|
| Search | Global search |
| Notifications | Open notification panel |
| Help | Link to help center |
| Logout | Sign out |

---

## 3. Navigation Patterns

### 3.1 Desktop Sidebar

```
┌────────────────────────────────────────────────────┐
│ [Logo]                                    [≡] [🔔] │
├──────────┬─────────────────────────────────────────┤
│          │                                         │
│ Dashboard│         Main Content Area              │
│ ────────>│                                         │
│ Orders   │                                         │
│ Products │                                         │
│ Customers│                                         │
│          │                                         │
│ ──────── │                                         │
│ Settings │                                         │
│ Help     │                                         │
│          │                                         │
├──────────┤                                         │
│ [Avatar] │                                         │
│ User Name│                                         │
└──────────┴─────────────────────────────────────────┘
```

### 3.2 Mobile Tab Bar

```
┌─────────────────────────────────────────┐
│ [←] Page Title                    [···] │
├─────────────────────────────────────────┤
│                                         │
│                                         │
│           Main Content Area             │
│                                         │
│                                         │
├─────────────────────────────────────────┤
│  🏠    📦    ➕    👥    👤            │
│ Home  Orders  New  Users  Profile       │
└─────────────────────────────────────────┘
```

### 3.3 Breadcrumbs (Desktop)

```
Home > Orders > Order #123 > Edit
```

| Level | Example |
|-------|---------|
| Root | Home / Dashboard |
| Section | Orders |
| Detail | Order #123 |
| Action | Edit |

---

## 4. Content Organization

### 4.1 Page Templates

| Template | Usage | Sections |
|----------|-------|----------|
| List Page | Feature overview | Header, Filters, Table/Grid, Pagination |
| Detail Page | Single item view | Header, Info Sections, Actions, Related |
| Form Page | Create/Edit | Header, Form Fields, Submit Actions |
| Dashboard | Home/Overview | Stats, Charts, Quick Actions, Feed |

### 4.2 Content Hierarchy

| Level | Element | Purpose |
|-------|---------|---------|
| 1 | Page Title (H1) | Identifies the page |
| 2 | Section Title (H2) | Groups related content |
| 3 | Subsection (H3) | Further breakdown |
| 4 | Labels | Field/item labels |
| 5 | Body Text | Content |
| 6 | Captions | Supporting text |

---

## 5. Search & Discovery

### 5.1 Global Search

| Feature | Behavior |
|---------|----------|
| Trigger | Keyboard shortcut (⌘K) or search icon |
| Scope | All searchable content |
| Results | Grouped by type |
| Recent | Show recent searches |

### 5.2 Filters & Sort

| Feature | Location |
|---------|----------|
| Quick Filters | Chips/tabs above content |
| Advanced Filters | Sidebar or dropdown |
| Sort Options | Dropdown in header |
| Active Filters | Visible chips with clear option |

---

## 6. User Roles & Access

### 6.1 Role-Based Navigation

| Role | Visible Nav Items | Restricted |
|------|-------------------|------------|
| User | Dashboard, [Feature], Profile | Settings, Admin |
| Manager | + Team section | Admin |
| Admin | All sections | None |

### 6.2 Permissions Matrix

| Feature | User | Manager | Admin |
|---------|------|---------|-------|
| View Dashboard | ✓ | ✓ | ✓ |
| Create [Item] | ✓ | ✓ | ✓ |
| Edit Own [Item] | ✓ | ✓ | ✓ |
| Edit Any [Item] | - | ✓ | ✓ |
| Delete [Item] | - | ✓ | ✓ |
| Manage Team | - | ✓ | ✓ |
| System Settings | - | - | ✓ |

---

## 7. Related Documents

| Document | Purpose |
|----------|---------|
| `screens/` | Individual screen specifications |
| `user-flows/` | User journey diagrams |
| `personas/` | User personas and needs |

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial architecture |

---

*Information Architecture complements ISO/IEC 29110-5-1-2 Software Design.*
