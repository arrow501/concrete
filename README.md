# Concrete

A brutalist–postmodern design system. One CSS file, one self-describing Markdown spec, one HTML shell that renders the spec live.

- `design-system.css` — tokens + components (zero dependencies)
- `DESIGN.md` — the spec, with inline live demos
- `index.html` — fetches the MD and renders it through the system's own CSS

## Use

```html
<link rel="stylesheet" href="design-system.css">
```

## View the showcase

```sh
python -m http.server 8000
```

Then open <http://localhost:8000>. The page renders `DESIGN.md` through `design-system.css` — the spec is the showcase.

## Theme

Light by default. Add `class="theme-dark"` to `<html>` to opt in to dark mode. The included shell has a toggle pinned top-right that persists to `localStorage`.

## Type

- **Body:** Spectral
- **Display (H1):** Fraunces (variable, with SOFT + WONK axes)
- **UI / labels / code:** JetBrains Mono

Loaded from Google Fonts in `index.html`.
