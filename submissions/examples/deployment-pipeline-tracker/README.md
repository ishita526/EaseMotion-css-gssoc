# Deployment Pipeline Progress Tracker

A CI/CD-inspired deployment tracker component that visualizes build and deployment stages.

## Features

- Pipeline timeline with vertical connecting lines
- Four deployment stages: Build, Tests, Deploy, Verification
- Status indicators: completed (green), active (blue), pending (gray), failed (red)
- Active stage pulse animation
- Card hover lift with border glow
- Fade-in entrance animation
- Responsive design
- `prefers-reduced-motion` support
- Pure HTML + CSS — no JavaScript

## Files

- `demo.html` — standalone demo with a 4-stage pipeline
- `style.css` — complete styling

## Usage

1. Copy `demo.html` and `style.css` into your project.
2. Open `demo.html` directly in a browser — no build step or server required.

```html
<div class="dp-card">
  <div class="dp-header">
    <h3 class="dp-title">Deployment Pipeline</h3>
    <span class="dp-status success">Success</span>
  </div>
  <div class="dp-pipeline">
    <div class="dp-step completed">
      <div class="dp-marker"><span class="dp-icon">✓</span></div>
      <div class="dp-content">
        <h4 class="dp-step-title">Build</h4>
        <p class="dp-step-desc">Completed in 24s</p>
      </div>
    </div>
    <!-- …more steps… -->
  </div>
</div>
```

## Use Cases

- DevOps dashboards
- Deployment monitoring
- SaaS admin panels
- CI/CD visualizations

## Why it fits EaseMotion CSS

- **Reusable component** — self-contained with the `dp-` class prefix
- **Animation-first** — pulse on the active step, fade-in entrance, hover transitions
- **Human-readable classes** — `dp-step`, `dp-status`, `completed`, `active` are self-documenting
- **Developer-focused aesthetic** — mirrors real CI/CD dashboards like GitHub Actions and Vercel
