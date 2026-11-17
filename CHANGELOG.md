# Changelog

All notable changes to **basic-ds** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

---

## [2.0.0] — 2026-11-17

### Added
- New modular Sass architecture: `abstracts/`, `base/`, `layout/`, `components/`, `utilities/`, `themes/`
- `abstracts/_variables.scss` — all Sass and CSS custom property tokens in one place
- `abstracts/_functions.scss` — `round-width()` grid helper using `sass:math`
- `abstracts/_mixins.scss` — `breakpoint()` and `fontSmooth` mixins
- `base/_reset.scss` — modern CSS reset (box-sizing, min-height, text-rendering)
- Full component suite:
  - `components/_buttons.scss` — variants, sizes (`xs`–`xl`), icon button, full-width, button group
  - `components/_forms.scss` — inputs, textarea, select, checkbox, radio, switch, label, hint, error states
  - `components/_cards.scss` — header, body, footer, image, and hoverable variants
  - `components/_alerts.scss` — success, error, warning, and info variants
  - `components/_badge.scss` — color badges and dot indicators
  - `components/_toast.scss` — toast notifications with dismiss buttons
  - `components/_spinner.scss` — CSS spinners and sizes
  - `components/_progress.scss` — progress bar with sizes and color fills
  - `components/_empty-state.scss` — placeholder views with icon, title, description, and action
  - `components/_navbar.scss` — responsive header navigation bar
  - `components/_sidenav.scss` — vertical sidebar navigation with active indicator
  - `components/_breadcrumb.scss` — breadcrumb trails
  - `components/_tabs.scss` — tabbed navigation lists and panels
  - `components/_pagination.scss` — numeric and directional pagination controls
  - `components/_menu.scss` — dropdown/action menus with headers and dividers
  - `components/_accordion.scss` — collapsible disclosure items
  - `components/_table.scss` — responsive tables with wrapper
  - `components/_list.scss` — structured item lists
  - `components/_avatar.scss` — user avatars with size scale and avatar groups
  - `components/_divider.scss` — subtle dividers and labeled dividers
  - `components/_tooltip.scss` — pure CSS tooltips with arrows
- Layout primitives:
  - `layout/_container.scss` — responsive centered `.container`, `.stack`, and `.cluster`
  - `layout/_grid.scss` — 12-column flexbox grid
  - `layout/_spacing.scss` — vertical spacing margin helpers
- Utilities:
  - `utilities/_spacing.scss` — padding, gap, and margin helpers
  - `utilities/_typography.scss` — text alignment, text colors, text transform, font weight
  - `utilities/_misc.scss` — `.hidden`, `.sr-only`, border utilities, border radius, shadows, z-index scale
- `themes/_default.scss` — token override layer for custom themes
- `docs/index.html` — interactive documentation showcase covering all 7 design system areas with copy-able code snippets and live interactive demos

### Changed
- Restructured flat `sass/` files into scoped sub-directories following the 7-1 pattern
- Replaced deprecated `@import` with `@use` / `@forward` throughout — each partial now self-imports its dependencies
- Migrated `round-width()` to use `sass:math` (`math.div`, `math.floor`) to silence Dart Sass 2.x deprecation warnings
- Moved `$grid-columns` Sass variable into `abstracts/_functions.scss` alongside its sole consumer
- Simplified `sass/basic-ds.scss` entry point to layer-level `@use` calls only
- Updated all CSS custom properties for buttons to use full `--btn-*` prefix consistently

### Removed
- Legacy flat-file partials at `sass/` root: `_buttons.scss`, `_colors.scss`, `_grid.scss`, `_spacing.scss`, `_typography.scss`

> [!IMPORTANT]
> **Breaking change:** Sass entry point has changed. If you were importing individual partials directly (e.g. `@use 'basic-ds/sass/_buttons'`), update your paths to the new structure (e.g. `@use 'basic-ds/sass/components/buttons'`).

---

## [1.1.0] — 2018-10-05

### Added
- Initial release with typography, spacing, grid, colors, and buttons

