<div class="band">CONCRETE · v0.3 · BRUTALIST–POSTMODERN · ONE FILE · NO JS</div>

# CONCRETE

<p class="dropcap">
A brutalist–postmodern design system. One CSS file. Zero JavaScript. Zero build step.
This document <em>is</em> the showcase. Every component below is rendered live with the
same stylesheet it documents. <span class="invert">Read it. See it.</span>
</p>

<div class="grid grid-3">
  <div class="box box-shadow"><strong class="mono upper">Structure</strong><br><span class="muted">is the decoration</span></div>
  <div class="box box-shadow"><strong class="mono upper">No radius</strong><br><span class="muted">corners stay sharp</span></div>
  <div class="box box-shadow"><strong class="mono upper">One voltage</strong><br><span class="muted">per screen</span></div>
</div>

<hr class="rule">

## 0 · North star

> Web 1 honesty, Web 3 self-awareness.
> Looks like raw HTML. Behaves like it was designed.

Three rules. If you break them, break them loudly:

1. **Structure is the decoration.** Borders, rules, and grids are not "chrome". They *are* the look.
2. **No round corners. Ever.** Radius is `0`.
3. **Color is a voltage, not a wash.** Paper + ink, then *one* sober accent per screen.

## 1 · Voice & feel

| Brutalism gives us | Postmodernism gives us |
|---|---|
| Raw materials (mono, serif, system fonts) | Quotation, irony, mixing eras |
| Visible grid | Off-grid tilts and offsets |
| Hard edges, no glassy shadows | Hard shadows as *stamps* |
| Monochrome by default | One sober accent |
| "It looks like a document" | "...that knows it's a document" |

<div class="callout">
<strong>Tone of copy:</strong> declarative. lowercase OR ALL CAPS. no marketing fluff.
Numbers and dates typed plainly. Mistakes (a strikethrough, a margin note) are welcome.
</div>

## 2 · Tokens

All tokens are CSS custom properties on `:root`. The default is **light**.
A `.theme-dark` class on `<html>` opts into dark mode. There is no `prefers-color-scheme` auto-flip.

### 2.1 Type

<table class="table">
<thead><tr><th>Token</th><th>Family</th><th>Use</th></tr></thead>
<tbody>
<tr><td><code>--font-body</code></td><td>Newsreader → Georgia → Times</td><td>paragraphs, blockquotes (default body)</td></tr>
<tr><td><code>--font-display</code></td><td>Fraunces (variable) → Newsreader</td><td>display H1</td></tr>
<tr><td><code>--font-mono</code></td><td>JetBrains Mono → system mono</td><td>H2/H3, UI, labels, code</td></tr>
</tbody></table>

Body sets at **19px / 1.6** for comfortable serif reading. Mono carries the *UI* register; serif carries the *document* register. The mix is the postmodern joke.

**Scale** (modular, 16px base):
`--t-xs 12 · --t-sm 14 · --t-base 16 · --t-md 20 · --t-lg 28 · --t-xl 40 · --t-xxl 64 · --t-mega 104`

### 2.2 Space (4px grid)

`--s-1 4 · --s-2 8 · --s-3 12 · --s-4 16 · --s-5 24 · --s-6 32 · --s-7 48 · --s-8 64 · --s-9 96`

<div class="callout callout-warn">
Never use a value off-grid. If you need 14px, use 12 or 16.<br>
<strong>The grid is the discipline.</strong>
</div>

### 2.3 Color: paper, ink, three sober accents

<div class="grid grid-2 mb-4">
  <div class="swatch">
    <div class="swatch-chip" style="background:var(--ink)"></div>
    <div class="swatch-meta"><strong>--ink</strong><span>#141210 · warm near-black</span></div>
  </div>
  <div class="swatch">
    <div class="swatch-chip" style="background:var(--paper)"></div>
    <div class="swatch-meta"><strong>--paper</strong><span>#f1ece1 · newsprint cream</span></div>
  </div>
  <div class="swatch">
    <div class="swatch-chip" style="background:var(--paper-2)"></div>
    <div class="swatch-meta"><strong>--paper-2</strong><span>#e4ddcc · recessed surface</span></div>
  </div>
  <div class="swatch">
    <div class="swatch-chip" style="background:var(--accent)"></div>
    <div class="swatch-meta"><strong>--accent</strong><span>ochre · primary accent, hover, focus</span></div>
  </div>
  <div class="swatch">
    <div class="swatch-chip" style="background:var(--link)"></div>
    <div class="swatch-meta"><strong>--link</strong><span>deep teal · links, callouts</span></div>
  </div>
  <div class="swatch">
    <div class="swatch-chip" style="background:var(--alert)"></div>
    <div class="swatch-meta"><strong>--alert</strong><span>oxblood · stamps, warnings</span></div>
  </div>
</div>

<p><strong>Fixed-contrast tokens.</strong> <code>--on-accent</code> stays dark in both themes, so voltage backgrounds can never become low-contrast. Use it on any colored fill.</p>

<p><strong>Rule:</strong> one sober accent per view. Mixing two = a deliberate, considered act.</p>

### 2.4 Structure

- `--border-w: 2px` · `--border-w-fat: 6px`
- `--radius: 0` &nbsp; *(never override)*
- `--shadow-hard: 6px 6px 0 0 ink` (a stamp, not a glow)

## 3 · Components

### 3.1 Box: the workhorse

<div class="grid grid-2 mb-4">
  <div class="box">.box</div>
  <div class="box box-shadow">.box .box-shadow</div>
  <div class="box box-fat">.box .box-fat</div>
  <div class="box box-shadow-fat">.box .box-shadow-fat</div>
  <div class="box box-invert">.box .box-invert</div>
  <div class="box box-paper-2">.box .box-paper-2</div>
  <div class="box box-accent">.box .box-accent</div>
  <div class="box box-soft">.box .box-soft</div>
</div>

```html
<div class="box box-shadow">…</div>
```

### 3.2 Button

<p>
<a class="btn">.btn</a>
<a class="btn btn-primary">.btn-primary</a>
<a class="btn btn-accent">.btn-accent</a>
<a class="btn btn-ghost">.btn-ghost</a>
</p>

Active state physically depresses into its shadow. Press one.

### 3.3 Input

<div class="grid grid-2 mb-4">
  <input class="input" placeholder="type here. focus draws the accent." />
  <select class="input"><option>select an option</option><option>option two</option></select>
</div>
<textarea class="input" rows="3" placeholder="textarea. same class."></textarea>

### 3.4 Badge & Stamp

<p>
<span class="badge">badge</span>
<span class="badge badge-accent">accent</span>
<span class="badge badge-soft">soft</span>
<span class="badge">v0.3</span>
&nbsp;&nbsp;
<span class="stamp">approved</span>
</p>

### 3.5 Nav

<nav class="nav">
  <span class="brand">Concrete.</span>
  <a href="#">work</a>
  <a href="#">writing</a>
  <a href="#">contact</a>
  <a href="#" class="btn btn-ghost" style="padding:6px 12px">log in</a>
</nav>

### 3.6 Callouts

<div class="callout">Default callout. Deep-teal side bar, the cool civic note.</div>
<div class="callout callout-warn"><strong>Warning.</strong> Oxblood bar. Use for destructive moves.</div>
<div class="callout callout-yay"><strong>Note.</strong> Ochre bar. Use for the good news.</div>

### 3.7 Table

<table class="table">
<thead><tr><th>Class</th><th>What it does</th><th>Notes</th></tr></thead>
<tbody>
<tr><td><code>.btn</code></td><td>Inverted-shadow button</td><td>Press depresses 4px</td></tr>
<tr><td><code>.input</code></td><td>Form field</td><td>Focus draws the ochre shadow</td></tr>
<tr><td><code>.callout</code></td><td>Side-barred note</td><td>+ <code>.callout-warn</code>, <code>.callout-yay</code></td></tr>
<tr><td><code>.swatch</code></td><td>Color spec row</td><td>Chip on left, meta on right</td></tr>
</tbody></table>

### 3.8 Band

<div class="band">SHIPPING IS A FEATURE · SHIPPING IS A FEATURE · SHIPPING IS A FEATURE</div>
<div class="band band-accent">FOCUS · FOCUS · FOCUS · FOCUS · FOCUS · FOCUS · FOCUS · FOCUS</div>

## 4 · Layout language

- Container: `.container` (max 1200px).
- Grids: `.grid.grid-2 / grid-3 / grid-12`.
- **Asymmetry helpers** (the postmodern handshake):
  - `.offset-up` / `.offset-down`: translate ±12px
  - `.tilt-l` / `.tilt-r`: rotate ±1.2°

<div class="grid grid-3 mb-4">
  <div class="box box-shadow tilt-l">.tilt-l</div>
  <div class="box box-shadow offset-up">.offset-up</div>
  <div class="box box-shadow tilt-r">.tilt-r</div>
</div>

<div class="callout">Use one offset or tilt per section, not five. More than that just looks broken.</div>

## 5 · Type rules

- H1 is **Fraunces display**, very large, tight leading (`0.88`), slight WONK + SOFT axes for character.
- H2/H3 are **mono, uppercase**. H2 has a small ochre square preceding it as an editor's mark.
- Body is **Newsreader at 17px**. Never below 15px for paragraphs.
- Line length capped at `68ch`. Brutalism is not unreadable.
- Drop-cap via `.dropcap`: the first letter renders in ochre, 5em, serif.

## 6 · Motion

Default: **none**. Brutalist UI is immediate.

Allowed:

- Button `:active` depresses by 4px (built in).
- `.hover-jitter`: 220ms 3-step jitter. <span class="badge hover-jitter">hover me</span> One per page, max.
- Respect `prefers-reduced-motion`.

## 7 · Accessibility

- Contrast: ink-on-paper is **>15:1**. Accents are decorative; never rely on them alone for meaning.
- Focus states are **visible**: a 6px ochre offset shadow + ochre border. Do not remove outlines.
- All interactive components keyboard-reachable with no JS.
- Dark mode is **opt-in** via `<html class="theme-dark">`. The toggle in this page persists to `localStorage`.

## 8 · Anti-patterns

<div class="box box-fat" style="border-color:var(--alert)">

Do **not**:

- Round any corner.
- Use soft drop shadows (gaussian blur). Shadows are hard offsets.
- Stack three accents at once. Pick one.
- Use a gradient. Ever.
- Center-align body copy.
- Apologize for the borders.

</div>

## 9 · Usage

```html
<link rel="stylesheet" href="design-system.css">
```

That's the install. There is no step two.

To render *this document* with the system, open `index.html`. It fetches `DESIGN.md`,
parses it with [marked](https://marked.js.org), and applies `design-system.css`.
The MD file is the source of truth and the live showcase.

## 10 · Versioning

`v0.3`. Palette refit to ochre + deep teal + oxblood (was vermilion/yellow/pink).
Body type now Newsreader; display now Fraunces. Light is default; dark is opt-in.
Tokens are stable; component class names will not break in 0.x patches.

<hr class="rule">

<div class="grid grid-2 mt-6 mb-6">
  <div>
    <p class="mono upper muted">end of document</p>
    <p class="serif" style="font-size:var(--t-lg);line-height:1.15">"A building should look like what it is."<br>And so should a website.</p>
  </div>
  <div class="right">
    <span class="stamp">v0.3</span>
  </div>
</div>

<hr class="rule-thin">

<div class="grid grid-2 mb-8">
  <div class="mono upper" style="font-size:var(--t-sm);letter-spacing:0.08em">
    <a href="https://github.com/arrow501/concrete">github.com/arrow501/concrete</a><br>
    <a href="https://concrete.pages.dev">concrete.pages.dev</a>
  </div>
  <div class="right mono upper muted" style="font-size:var(--t-sm);letter-spacing:0.08em">
    by Arrow · 2026
  </div>
</div>
