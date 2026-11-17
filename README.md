# basic-ds

A lightweight, **Sass-based CSS design system** with design tokens, utility classes, and reusable UI components.

[![npm](https://img.shields.io/npm/v/basic-ds)](https://www.npmjs.com/package/basic-ds)
[![license](https://img.shields.io/npm/l/basic-ds)](./LICENSE)

---

## Features

- **Design tokens** — colors, spacing, typography, shadows, and border radius as CSS custom properties
- **Components** — complete UI suite: forms, feedback, navigation, content, and actions
- **Utilities** — spacing, typography, alignment, truncation, borders, shadows, z-index, visibility (`.hidden`, `.sr-only`), and colors
- **Layout helpers** — 12-column flexbox grid, flex stack, cluster, and container
- **Theme layer** — override any token without touching source files
- **Modular Sass** — `@use` / `@forward` architecture, zero global leakage
- Ships compiled CSS + source Sass

---

## Installation

```bash
npm install basic-ds
```

---

## Usage

### Use the compiled CSS

The quickest way — just link the stylesheet:

```html
<link rel="stylesheet" href="node_modules/basic-ds/css/basic-ds.css" />
```

Or import it in your JS bundler:

```js
import 'basic-ds/css/basic-ds.css';
```

### Use the Sass source

Import the full system into your own Sass entry point:

```scss
@use 'basic-ds/sass/basic-ds';
```

Import individual layers only:

```scss
// Tokens (CSS custom properties)
@use 'basic-ds/sass/utilities';

// Just components
@use 'basic-ds/sass/components';
```

Import a specific partial:

```scss
@use 'basic-ds/sass/components/buttons';
@use 'basic-ds/sass/components/cards';
```

---

## Customisation

Override design tokens in your own stylesheet **after** importing basic-ds:

```css
:root {
  --color-primary: #6366f1;
  --radius: 0.5em;
  --text-scale-ratio: 1.25;
  --space-unit: 1.125em;
}
```

Or use the Sass theme layer before the rest of the system compiles:

```scss
// your-theme.scss
@use 'basic-ds/sass/abstracts' as *;

// then override tokens …
```

---

## Sass Architecture

```
sass/
├── abstracts/        # Variables, functions, mixins — no CSS output
│   ├── _variables.scss
│   ├── _functions.scss
│   ├── _mixins.scss
│   └── _index.scss
├── base/             # Reset + base typography
│   ├── _reset.scss
│   ├── _typography.scss
│   └── _index.scss
├── layout/           # Container, stack, cluster, grid, spacing helpers
│   ├── _container.scss
│   ├── _grid.scss
│   ├── _spacing.scss
│   └── _index.scss
├── components/       # Reusable UI components
│   ├── _accordion.scss
│   ├── _alerts.scss
│   ├── _avatar.scss
│   ├── _badge.scss
│   ├── _breadcrumb.scss
│   ├── _buttons.scss
│   ├── _cards.scss
│   ├── _divider.scss
│   ├── _empty-state.scss
│   ├── _forms.scss
│   ├── _list.scss
│   ├── _menu.scss
│   ├── _navbar.scss
│   ├── _pagination.scss
│   ├── _progress.scss
│   ├── _sidenav.scss
│   ├── _spinner.scss
│   ├── _table.scss
│   ├── _tabs.scss
│   ├── _toast.scss
│   ├── _tooltip.scss
│   └── _index.scss
├── utilities/        # Colors, spacing, typography, and misc CSS helpers
│   ├── _colors.scss
│   ├── _misc.scss
│   ├── _spacing.scss
│   ├── _typography.scss
│   └── _index.scss
├── themes/           # Token override layer
│   ├── _default.scss
│   └── _index.scss
└── basic-ds.scss     # Main entry point
```

---

## Component Areas & Classes

| Area | Components / Classes |
| --- | --- |
| **Forms** | `.form-group`, `.form-label`, `.form-hint`, `.form-error`, `.input`, `.select`, `.textarea`, `.check-group`, `.radio-group`, `.switch` |
| **Feedback** | `.alert` (success, error, warning, info), `.badge` (dot & color variants), `.toast`, `.spinner`, `.progress`, `.empty-state` |
| **Navigation** | `.navbar`, `.sidenav`, `.breadcrumb`, `.tabs`, `.pagination`, `.menu` |
| **Content** | `.card` (header, body, footer, hover), `.accordion`, `.table-wrap`, `.table`, `.list`, `.avatar` & `.avatar-group`, `.divider` (plain & labeled), `.tooltip-wrap` & `.tooltip` |
| **Actions** | `.btn` (primary, secondary, accent, ghost, link, icon), sizes (`.btn--xs` to `.btn--xl`), `.btn--full`, `.btn-group`, loading states |
| **Layout** | `.container`, `.stack`, `.cluster`, `.flex-grid` (`.col--1` to `.col--12`), margin & padding helpers |
| **Utilities** | Visibility (`.hidden`, `.sr-only`), text alignment, `.truncate`, borders (`.border`, `.border-0`), `.rounded`, `.rounded-full`, shadows (`.shadow-sm`, `.shadow-md`, `.shadow-lg`), and `.z-0` to `.z-50` |

---

## Components

### Buttons

```html
<button class="btn btn--primary">Primary</button>
<button class="btn btn--secondary">Secondary</button>
<button class="btn btn--accent">Accent</button>
<button class="btn btn--primary btn--sm">Small</button>
<button class="btn btn--primary btn--lg">Large</button>
<button class="btn btn--primary" disabled>Disabled</button>

<!-- Full-width -->
<button class="btn btn--primary btn--full-width">Full width</button>

<!-- Group -->
<div class="btns">
  <button class="btn btn--primary">Save</button>
  <button class="btn btn--secondary">Cancel</button>
</div>
```

### Forms

```html
<div class="form-group">
  <label for="email">Email</label>
  <input type="email" id="email" placeholder="you@example.com" />
</div>
```

### Cards

```html
<div class="card">
  <div class="card__header">
    <p class="card__title">Card Title</p>
  </div>
  <div class="card__body">Card content goes here.</div>
  <div class="card__footer">
    <button class="btn btn--primary btn--sm">Action</button>
  </div>
</div>
```

### Alerts

```html
<div class="alert alert--success">Changes saved successfully.</div>
<div class="alert alert--error">Something went wrong.</div>
<div class="alert alert--warning">Please review before continuing.</div>
```

---

## Grid

12-column flexbox grid with CSS custom property gap control.

```html
<div class="flex-grid">
  <div class="col col--4">One third</div>
  <div class="col col--4">One third</div>
  <div class="col col--4">One third</div>
</div>
```

Available column spans: `col--1` through `col--12`. Columns are full-width by default and stack naturally on small screens.

---

## Development

```bash
# Install dependencies
npm install

# Build CSS from Sass
npm run build

# Watch for changes
npm run watch
```

Build output goes to `css/`:

| File | Description |
|---|---|
| `basic-ds.css` | Expanded, autoprefixed CSS |
| `basic-ds.css.map` | Source map |
| `basic-ds.min.css` | Minified CSS |

---

## Docs

Open `docs/index.html` in a browser for a live showcase of all components and tokens.

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for the full release history.

---

## License

[MIT](./LICENSE) © Razan Azuddin