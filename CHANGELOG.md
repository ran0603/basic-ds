# Changelog

All notable changes to **basic-ds** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Added
- New modular Sass architecture: `abstracts/`, `base/`, `layout/`, `components/`, `utilities/`, `themes/`
- `_reset.scss` — modern CSS reset in `base/`
- `_cards.scss` and `_alerts.scss` components
- `_forms.scss` component with focus and error states
- Utility partials: `_colors.scss`, `_spacing.scss`, `_typography.scss`
- `themes/_default.scss` for token overrides
- `docs/index.html` live component showcase

### Changed
- Migrated flat Sass files into scoped sub-directories
- Replaced `@import` with `@use` / `@forward` throughout
- Moved grid `round-width()` function to `abstracts/_functions.scss`
- Moved all CSS custom properties to `abstracts/_variables.scss` and `utilities/_colors.scss`

### Removed
- Legacy flat-file imports (`_buttons.scss`, `_colors.scss`, etc. at root of `sass/`)

---

## [1.1.0] — 2018-10-05

### Added
- Initial release with typography, spacing, grid, colors, and buttons

