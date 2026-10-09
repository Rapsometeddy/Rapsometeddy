# Rapsometeddy Ecosystem Design System

Version: 1.0 · Mobile-first · Free-first

## Identity
- Primary mark: crowned **R**. Use the SVG in `assets/crowned-r.svg`; do not substitute emoji for the production logo.
- Core palette: near-black canvas, layered charcoal surfaces, vivid purple accent, lavender secondary accent, high-contrast white text.
- Shared signature: **BUILD • LEARN • CREATE • INVEST**.
- Each app keeps its own product name, iconography, workflows, and domain-specific layout.

## Tokens
```css
:root {
  color-scheme: dark;
  --rt-bg: #09070f;
  --rt-surface: #12101c;
  --rt-surface-raised: #1a1628;
  --rt-border: #302744;
  --rt-purple: #8b5cf6;
  --rt-purple-strong: #7c3aed;
  --rt-lavender: #c4b5fd;
  --rt-text: #f7f4ff;
  --rt-muted: #aaa3ba;
  --rt-success: #34d399;
  --rt-warning: #fbbf24;
  --rt-danger: #fb7185;
  --rt-radius-card: 18px;
  --rt-radius-control: 12px;
  --rt-focus: 0 0 0 3px #c4b5fd66;
}
```

## Layout rules
1. Design for a 360px-wide Android viewport first; avoid horizontal page scrolling.
2. Main content uses a fluid container with 16px mobile gutters and a readable maximum width.
3. Controls have a minimum 44px touch target, visible focus states, and labels that do not rely on color alone.
4. Use responsive grids that collapse to one column on small screens.
5. Keep key actions near the top; use sticky navigation only when it does not obscure content.
6. Respect `prefers-reduced-motion`; use subtle transitions (150–240ms) and avoid decorative motion that slows low-end phones.
7. Images must be real local assets or dependable remote assets with fallbacks, meaningful alt text, and sensible dimensions. Do not ship empty image placeholders.

## Component language
- Cards: charcoal surface, subtle purple border, restrained highlight.
- Primary action: purple fill with readable white text.
- Secondary action: transparent/charcoal with border.
- Status: text + icon, never color alone.
- Charts: preserve actual data and loading/error states; never replace operational data with fabricated demo values.
- Empty states explain the next real action.
- Forms show validation and preserve user input on recoverable errors.

## Product personalities
- Ecosystem Hub: overview, app directory, connection/health status.
- Anime Studio: cinematic art direction and a creation timeline; preserve generation, approval, export, and publish gates.
- STUDIO R / Voice Studio: audio-workstation energy; preserve actual generation and playback controls.
- Trader: compact market workstation; preserve read-only data provenance and paper-trading boundaries.
- Business OS / ProfitMate: practical operations and finance dashboards.
- Content Machine / HQ Bot: automation pipeline, queue and delivery statuses.
- Sports Predictor: statistical analysis and transparent model assumptions, not betting functionality.

## Implementation guardrails
- Inspect existing code before editing; make small, reviewable commits.
- Do not remove working APIs, database calls, auth, generation, exports, or automation.
- Keep credentials server-side; never expose service-role or secret keys to browser code.
- Prefer existing dependencies and free-tier services. Avoid adding a library for a small CSS interaction.
- Verify build/deployment state before calling a change live. A Git commit is not proof of a successful deployment.
