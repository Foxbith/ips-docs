# Accessibility Specification

> WCAG Compliance and Inclusive Design for [PROJECT_NAME]

---

## Metadata

```yaml
project: "[PROJECT_NAME]"
version: "1.0"
last_updated: "YYYY-MM-DD"
author: "[NAME]"
status: "Draft"
target_level: "WCAG 2.1 AA"
```

---

## 1. Compliance Target

### 1.1 Standard
| Attribute | Value |
|-----------|-------|
| Standard | WCAG 2.1 |
| Target Level | AA |
| Legal Requirements | [ADA / Section 508 / EN 301 549 / None] |

### 1.2 Scope
| Platform | Compliance Required |
|----------|---------------------|
| Web Application | ✓ Full |
| Mobile App (iOS) | ✓ Full |
| Mobile App (Android) | ✓ Full |
| Marketing Website | ✓ Full |
| Admin Panel | Partial (internal) |

---

## 2. Perceivable

### 2.1 Text Alternatives (1.1)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| Images have alt text | `<img alt="description">` | [ ] |
| Decorative images | `alt=""` or CSS background | [ ] |
| Complex images | Long description or text equivalent | [ ] |
| Icons with meaning | aria-label or visible text | [ ] |
| Audio/Video captions | Provide captions/transcripts | [ ] |

### 2.2 Color & Contrast (1.4)

| Requirement | Minimum | Status |
|-------------|---------|--------|
| Normal text contrast | 4.5:1 | [ ] |
| Large text contrast (18px+ bold, 24px+) | 3:1 | [ ] |
| UI component contrast | 3:1 | [ ] |
| Focus indicator contrast | 3:1 | [ ] |
| Color not sole indicator | Use icons/text too | [ ] |

**Color Contrast Verification:**
| Element | Foreground | Background | Ratio | Pass |
|---------|------------|------------|-------|------|
| Body text | #[XXX] | #[XXX] | [X.X]:1 | [ ] |
| Link text | #[XXX] | #[XXX] | [X.X]:1 | [ ] |
| Button primary | #[XXX] | #[XXX] | [X.X]:1 | [ ] |
| Error text | #[XXX] | #[XXX] | [X.X]:1 | [ ] |

### 2.3 Text Sizing (1.4.4)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| 200% zoom works | Responsive layout | [ ] |
| Text resizable | Use rem/em, not px | [ ] |
| No horizontal scroll at 320px | Reflow content | [ ] |

---

## 3. Operable

### 3.1 Keyboard Access (2.1)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| All functions via keyboard | Tab, Enter, Space, Arrow keys | [ ] |
| No keyboard traps | Escape closes modals | [ ] |
| Skip links | "Skip to content" link | [ ] |
| Visible focus indicator | Outline or ring | [ ] |

**Keyboard Shortcuts:**
| Action | Shortcut | Scope |
|--------|----------|-------|
| Search | ⌘K / Ctrl+K | Global |
| Close modal | Escape | Modal |
| Navigate tabs | Arrow keys | Tab group |
| Submit form | Enter | Form |

### 3.2 Focus Management

| Scenario | Focus Behavior |
|----------|----------------|
| Modal opens | Focus first focusable element |
| Modal closes | Return focus to trigger |
| Page navigation | Focus main heading or skip link |
| Error on submit | Focus first error field |
| Dynamic content | Announce via aria-live |

### 3.3 Touch Targets (2.5.5)

| Requirement | Minimum Size | Status |
|-------------|--------------|--------|
| Touch targets | 44x44px | [ ] |
| Spacing between targets | 8px | [ ] |

---

## 4. Understandable

### 4.1 Language (3.1)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| Page language | `<html lang="en">` | [ ] |
| Language changes | `lang` attribute on element | [ ] |

### 4.2 Predictable (3.2)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| Consistent navigation | Same location across pages | [ ] |
| Consistent identification | Same labels for same functions | [ ] |
| No unexpected context change | User initiates changes | [ ] |

### 4.3 Input Assistance (3.3)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| Error identification | Clear error messages | [ ] |
| Labels/instructions | All inputs have labels | [ ] |
| Error suggestion | Suggest corrections | [ ] |
| Error prevention | Confirm destructive actions | [ ] |

**Form Error Patterns:**
```html
<!-- Inline error -->
<input id="email" aria-invalid="true" aria-describedby="email-error">
<span id="email-error" role="alert">Please enter a valid email</span>

<!-- Error summary -->
<div role="alert" aria-labelledby="error-heading">
  <h2 id="error-heading">Please fix the following errors:</h2>
  <ul>
    <li><a href="#email">Email is required</a></li>
  </ul>
</div>
```

---

## 5. Robust

### 5.1 Parsing & Compatibility (4.1)

| Requirement | Implementation | Status |
|-------------|----------------|--------|
| Valid HTML | Pass W3C validator | [ ] |
| Unique IDs | No duplicate IDs | [ ] |
| ARIA valid | Correct roles/states | [ ] |
| Screen reader tested | VoiceOver, NVDA, TalkBack | [ ] |

---

## 6. ARIA Implementation

### 6.1 Landmark Regions

```html
<header role="banner">...</header>
<nav role="navigation">...</nav>
<main role="main">...</main>
<aside role="complementary">...</aside>
<footer role="contentinfo">...</footer>
```

### 6.2 Common ARIA Patterns

**Modal Dialog:**
```html
<div role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <h2 id="modal-title">Dialog Title</h2>
  ...
</div>
```

**Tab Panel:**
```html
<div role="tablist">
  <button role="tab" aria-selected="true" aria-controls="panel1">Tab 1</button>
  <button role="tab" aria-selected="false" aria-controls="panel2">Tab 2</button>
</div>
<div role="tabpanel" id="panel1">Content 1</div>
<div role="tabpanel" id="panel2" hidden>Content 2</div>
```

**Live Region (Dynamic Updates):**
```html
<div aria-live="polite" aria-atomic="true">
  <!-- Updated content announced by screen reader -->
</div>
```

---

## 7. Testing

### 7.1 Automated Testing

| Tool | Purpose | Frequency |
|------|---------|-----------|
| axe-core | Automated a11y scan | Every PR |
| Lighthouse | Performance + a11y | Weekly |
| Pa11y | CI integration | Every build |
| WAVE | Browser extension | Manual |

### 7.2 Manual Testing

| Test | Tool | Frequency |
|------|------|-----------|
| Keyboard navigation | Keyboard only | Every feature |
| Screen reader (Mac) | VoiceOver | Every release |
| Screen reader (Windows) | NVDA | Every release |
| Screen reader (Mobile) | TalkBack/VoiceOver | Every release |
| Color contrast | Contrast checker | Design review |
| Zoom 200% | Browser zoom | Every feature |

### 7.3 User Testing

| Method | Participants | Frequency |
|--------|--------------|-----------|
| Usability with AT users | 3-5 users | Quarterly |
| Expert review | Accessibility specialist | Major releases |

---

## 8. Remediation Plan

### 8.1 Known Issues

| Issue | WCAG Criterion | Severity | Status | Target Fix |
|-------|----------------|----------|--------|------------|
| [Issue 1] | [X.X.X] | [High/Med/Low] | [Open] | [Sprint X] |

### 8.2 Roadmap

| Phase | Focus | Timeline |
|-------|-------|----------|
| Phase 1 | Critical issues (A) | [Date] |
| Phase 2 | AA compliance | [Date] |
| Phase 3 | Enhanced experience | [Date] |

---

## 9. Resources

### 9.1 References
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
- [Inclusive Components](https://inclusive-components.design/)

### 9.2 Tools
- [axe DevTools](https://www.deque.com/axe/)
- [WAVE Browser Extension](https://wave.webaim.org/)
- [Contrast Checker](https://webaim.org/resources/contrastchecker/)

---

## Document History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | YYYY-MM-DD | [Name] | Initial specification |

---

*Accessibility specification complements ISO/IEC 29110-5-1-2 Software Design.*
