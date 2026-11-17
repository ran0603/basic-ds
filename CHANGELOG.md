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
- `components/_cards.scss` — card with header, body, and footer regions
- `components/_alerts.scss` — success, error, and warning alert variants
- `components/_forms.scss` — input, textarea, select with focus and error states
- `utilities/_spacing.scss` — padding and gap utility classes
- `utilities/_typography.scss` — text-align, color, transform, and weight helpers
- `themes/_default.scss` — token override layer for custom themes
- `docs/index.html` — live component showcase (typography, colors, buttons, alerts, cards, forms, grid)

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

