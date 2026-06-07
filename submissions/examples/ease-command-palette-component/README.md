# Ease Command Palette Component

## What does this do?
A developer-focused command console interface that features quick access to searchable links, keyboard shortcuts, config options, category dividers, and theme overlays, optimized for quick keyboard-driven navigation (Ctrl/⌘ + K).

---

## Why is it useful?
Command palettes are a powerful UX pattern popularized by tools like VS Code, Notion, and Slack. They reduce layout navigation friction, allow searching through hundreds of configurations instantly, and improve workflow efficiency. This component is zero-dependency, works fully offline with responsive grid scaling, and supports custom CSS variables to adapt colors, backdrops, and blur parameters seamlessly.

---

## How is it used?

### Basic HTML Structure

```html
<!-- Backdrop Overlay -->
<div class="ease-cp-overlay" id="command-palette">
  
  <!-- Dialogue Card Container -->
  <div class="ease-cp-container">
    
    <!-- Search Bar Wrapper -->
    <div class="ease-cp-search-wrap">
      <div class="ease-cp-search-icon">
        <!-- SVG Search Icon -->
      </div>
      <input type="text" class="ease-cp-input" placeholder="Type a command...">
      <span class="ease-cp-esc-badge">esc</span>
    </div>

    <!-- Commands List -->
    <div class="ease-cp-list">
      
      <!-- Group Header -->
      <div class="ease-cp-group-title">Navigation</div>
      
      <!-- List Item (Add 'active' for highlight selection state) -->
      <div class="ease-cp-item active">
        <div class="ease-cp-item-left">
          <span class="ease-cp-item-icon">
            <!-- SVG Icon -->
          </span>
          <div class="ease-cp-item-meta">
            <span class="ease-cp-item-text">Go to Dashboard</span>
            <span class="ease-cp-item-subtext">Open main dashboard overview</span>
          </div>
        </div>
        <div class="ease-cp-item-shortcut">
          <kbd>g</kbd> <kbd>d</kbd>
        </div>
      </div>

    </div>

    <!-- Footer hints -->
    <div class="ease-cp-footer">
      <span class="ease-cp-footer-hint"><kbd>↑↓</kbd> to navigate</span>
      <span class="ease-cp-footer-hint"><kbd>↵</kbd> to select</span>
    </div>

  </div>
</div>
```

---

### Basic Javascript Controller

```javascript
// Open palette with theme modifier
function openPalette(themeClass = '') {
  const palette = document.getElementById('command-palette');
  palette.className = 'ease-cp-overlay';
  if (themeClass) palette.classList.add(themeClass);
  palette.classList.add('ease-cp--open');
}

// Global toggle hook (Ctrl+K or Cmd+K)
document.addEventListener('keydown', (e) => {
  if ((e.ctrlKey || e.metaKey) && e.key.toLowerCase() === 'k') {
    e.preventDefault();
    openPalette();
  }
});
```

---

## Features
- **Keyboard-Driven UX**: Full support for Keyboard arrow keys (`ArrowUp`/`ArrowDown`) navigation, `Enter` key execution, and `Escape` key close handlers.
- **Shortcut Triggers**: Global listener for `Ctrl + K` or `Cmd + K` to toggle the dialog panel.
- **Instant Query Filtering**: Search input queries filter the listed commands dynamically in real-time.
- **Glassmorphism Backdrop**: Semi-transparent backing with `backdrop-filter: blur(8px)` overlays.
- **Clean Command Categories**: Visual group dividers (`.ease-cp-group-title`) and `<kbd>` keys labels.
- **Responsive Layout**: Rescales dialogue card margins and category lists size to fit small mobile viewports.

---

## Variants

1. **Default Palette**: Elegant dark transparent backdrop overlay with a clean white console container.
2. **Dark Mode Palette** (`.ease-cp--dark`): Deep slate container backgrounds, high contrast text offsets, and dark footer sections.
3. **Light Mode Palette** (`.ease-cp--light`): Simple light gray container borders, native white surfaces.
4. **Minimal Palette** (`.ease-cp--minimal`): Spaciously designed flat palette container with borderless search inputs and footer rows.
5. **Gradient Accent Palette** (`.ease-cp--gradient`): Linear gradient accent borders, gradient highlights on item hover, and gradient icon color masks.

---

## Command Types

- **Search Commands**: Items dedicated to system search fields.
- **Navigation Commands**: Redirect links leading to different views (Dashboard, settings, documentation).
- **Action Commands**: Triggers that execute workspace routines (Create new branch, add staging files, purge caches).
- **Shortcut Commands**: Items featuring inline `<kbd>` keyboard combination symbols.
- **Settings Commands**: Options adjusting profiles or toggling themes.

---

## Class Glossary

- **`.ease-cp-overlay`**: Backdrop overlay wrapper. Use `.ease-cp--open` to open.
- **`.ease-cp-container`**: Main dialogue container card.
- **`.ease-cp-search-wrap`**: Outer wrap for search field.
- **`.ease-cp-input`**: Plain search query input field.
- **`.ease-cp-list`**: Vertical command track.
- **`.ease-cp-group-title`**: Muted category header titles.
- **`.ease-cp-item`**: Single command row. Use `.active` class to trigger focus styles.
- **`.ease-cp-item-shortcut`**: Element container holding `<kbd>` pills.
- **`.ease-cp-footer`**: Footer details showing key controls.

---

## Customization

You can override variable values in `:root` or wrap within specific target classes:

```css
:root {
  --cp-overlay-bg: rgba(15, 23, 42, 0.7); /* Darken command palette backdrop overlay */
  --cp-overlay-blur: 12px; /* Increase glassmorphism blur intensity */
  
  --cp-color-primary: #10b981; /* Emerald green primary accents */
}
```
