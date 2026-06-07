# Ease Sidebar Component

## What does this do?

A modern, animation-driven sidebar navigation component designed for dashboards, admin panels, and SaaS applications. It provides a structured layout for navigating between sections, with 10 ready-to-use variants, smooth expand/collapse animations, hover effects, active state highlighting, and responsive mobile off-canvas behavior.

---

## Why is it useful?

Sidebars are a core navigation pattern in modern UI systems. They organize content hierarchies and improve navigation efficiency in complex applications. This component follows EaseMotion CSS principles by being animation-driven, reusable, responsive, and adaptable across multiple layouts and themes — all with zero external dependencies and CSS-first architecture.

---

## How is it used?

### Basic HTML Structure

```html
<aside class="ease-sb">
  <!-- Brand / Logo -->
  <div class="ease-sb-header">
    <div class="ease-sb-logo">
      <!-- SVG Icon -->
    </div>
    <div class="ease-sb-brand">
      <span class="ease-sb-brand-name">App Name</span>
      <span class="ease-sb-brand-tag">Dashboard v2.0</span>
    </div>
  </div>

  <!-- Profile Section (optional) -->
  <div class="ease-sb-profile">
    <div class="ease-sb-avatar">JD</div>
    <div class="ease-sb-profile-info">
      <span class="ease-sb-profile-name">Jane Doe</span>
      <span class="ease-sb-profile-role">Designer</span>
    </div>
  </div>

  <!-- Navigation Links -->
  <nav class="ease-sb-nav">
    <span class="ease-sb-section-title">Main</span>

    <a href="#" class="ease-sb-item active" data-tooltip="Dashboard">
      <span class="ease-sb-item-icon"><!-- SVG --></span>
      <span class="ease-sb-item-label">Dashboard</span>
      <span class="ease-sb-badge">3</span>
    </a>

    <a href="#" class="ease-sb-item" data-tooltip="Analytics">
      <span class="ease-sb-item-icon"><!-- SVG --></span>
      <span class="ease-sb-item-label">Analytics</span>
    </a>

    <hr class="ease-sb-divider" />

    <span class="ease-sb-section-title">Account</span>

    <a href="#" class="ease-sb-item" data-tooltip="Settings">
      <span class="ease-sb-item-icon"><!-- SVG --></span>
      <span class="ease-sb-item-label">Settings</span>
    </a>
  </nav>
</aside>
```

### Adding a Theme Variant

```html
<!-- Dark theme -->
<aside class="ease-sb ease-sb--dark">...</aside>

<!-- Gradient theme -->
<aside class="ease-sb ease-sb--gradient">...</aside>

<!-- Glassmorphism theme -->
<aside class="ease-sb ease-sb--glass">...</aside>

<!-- Floating + Dark combination -->
<aside class="ease-sb ease-sb--floating ease-sb--dark">...</aside>
```

### Collapsible Toggle (JavaScript)

```javascript
function toggleSidebar() {
  const sidebar = document.querySelector('.ease-sb');
  sidebar.classList.toggle('ease-sb--collapsed');
}
```

### Mobile Off-Canvas Toggle

```html
<!-- Overlay backdrop -->
<div class="ease-sb-overlay" id="sidebar-overlay"></div>

<!-- Off-canvas sidebar -->
<aside class="ease-sb ease-sb--offcanvas" id="sidebar">...</aside>

<script>
  function toggleMobile() {
    document.getElementById('sidebar').classList.toggle('ease-sb--open');
    document.getElementById('sidebar-overlay').classList.toggle('ease-sb-overlay--open');
  }
</script>
```

---

## Features

- **Smooth Expand/Collapse Animation**: Width transitions with cubic-bezier easing. Labels, badges, and profile info fade out gracefully.
- **Active State Indicator**: Highlighted background + colored left-edge bar on the active navigation item.
- **Hover Effects**: Background color transitions on navigation items with icon color shifts.
- **Icon-Only Tooltips**: `data-tooltip` attribute powered CSS tooltips appear on hover in icon-only mode.
- **Navigation Badges**: Inline notification count badges on navigation items.
- **Section Dividers**: Visual separators and section title labels for organizing nav groups.
- **Profile Section**: Optional avatar with name/role display.
- **Responsive Mobile**: Automatic off-canvas behavior below 768px viewport width.
- **Reduced Motion**: Respects `prefers-reduced-motion` media query by disabling all animations.
- **CSS Variables**: Fully customizable via CSS custom properties.
- **No External Dependencies**: Zero JavaScript frameworks, CSS libraries, or CDN dependencies.

---

## Variants

1. **Default Sidebar** — Clean base sidebar with full nav structure.
2. **Collapsible Sidebar** (`.ease-sb--collapsed`) — Smooth width transition to icon-only mode.
3. **Icon-Only Sidebar** (`.ease-sb--icon-only`) — Permanent compact mode with hover tooltips.
4. **Dark Sidebar** (`.ease-sb--dark`) — Deep dark theme with high contrast text.
5. **Light Sidebar** (`.ease-sb--light`) — Explicit clean white theme override.
6. **Gradient Sidebar** (`.ease-sb--gradient`) — Rich purple gradient background.
7. **Glassmorphism Sidebar** (`.ease-sb--glass`) — Frosted glass with backdrop-filter blur.
8. **Fixed Sidebar** (`.ease-sb--fixed`) — Pinned to viewport left edge on scroll.
9. **Floating Sidebar** (`.ease-sb--floating`) — Detached with margin, border-radius, and elevated shadow.
10. **Mobile Off-Canvas** (`.ease-sb--offcanvas`) — Slides in from left with blurred overlay.

---

## Layout Structure

```
┌─ ease-sb ──────────────────────────────┐
│  ┌─ ease-sb-header ──────────────────┐ │
│  │  [Logo]  Brand Name / Tag         │ │
│  └───────────────────────────────────┘ │
│  ┌─ ease-sb-profile ─────────────────┐ │
│  │  [Avatar]  Name / Role            │ │
│  └───────────────────────────────────┘ │
│  ┌─ ease-sb-nav ─────────────────────┐ │
│  │  Section Title                     │ │
│  │  [Icon]  Label         [Badge]     │ │
│  │  [Icon]  Label                     │ │
│  │  ─── divider ───                   │ │
│  │  Section Title                     │ │
│  │  [Icon]  Label                     │ │
│  └───────────────────────────────────┘ │
│  ┌─ ease-sb-footer ──────────────────┐ │
│  │  Footer content                    │ │
│  └───────────────────────────────────┘ │
└────────────────────────────────────────┘
```

---

## Class Glossary

| Class | Description |
|---|---|
| `.ease-sb` | Base sidebar container |
| `.ease-sb-header` | Brand/logo header section |
| `.ease-sb-logo` | Logo icon wrapper |
| `.ease-sb-brand` | Brand name + tagline container |
| `.ease-sb-brand-name` | Primary brand text |
| `.ease-sb-brand-tag` | Secondary tagline text |
| `.ease-sb-profile` | User profile section |
| `.ease-sb-avatar` | Circular avatar with initials |
| `.ease-sb-profile-info` | Name and role container |
| `.ease-sb-nav` | Navigation items wrapper |
| `.ease-sb-section-title` | Uppercase section divider label |
| `.ease-sb-item` | Single navigation link (add `.active` for active state) |
| `.ease-sb-item-icon` | Icon wrapper inside nav item |
| `.ease-sb-item-label` | Text label inside nav item |
| `.ease-sb-badge` | Notification count badge |
| `.ease-sb-divider` | Horizontal rule divider |
| `.ease-sb-footer` | Sidebar footer section |
| `.ease-sb-toggle` | Collapse/expand toggle button |
| `.ease-sb-overlay` | Off-canvas backdrop overlay |
| `.ease-sb-mobile-toggle` | Mobile hamburger button |

---

## Customization

Override CSS variables in `:root` or within a parent wrapper:

```css
:root {
  /* Sizing */
  --sb-width: 280px;
  --sb-width-collapsed: 64px;

  /* Timing */
  --sb-transition: 250ms ease;

  /* Colors */
  --sb-bg: #f8f9fa;
  --sb-text: #1a1a1a;
  --sb-item-active-text: #10b981;
  --sb-item-active-indicator: #10b981;
  --sb-primary: #10b981;

  /* Shadows */
  --sb-shadow: 0 1px 4px rgba(0, 0, 0, 0.08);
}
```

---

## Accessibility

- Uses semantic `<nav>` and `<aside>` elements
- Navigation items are `<a>` links for keyboard navigation
- `data-tooltip` attributes provide context in icon-only mode
- Respects `prefers-reduced-motion` for users with motion sensitivities
- Color contrast ratios maintained for both light and dark themes

---

Submitted under EaseMotion CSS project requirements.  
No external frameworks, libraries, or CDN dependencies used.  
Status: **Pending review**
