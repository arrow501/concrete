<div class="band" id="top">CONCRETE · v0.5 · BRUTALIST–POSTMODERN · ONE FILE · NO JS</div>

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
<tr><td><code>--font-body</code></td><td>Spectral → Iowan Old Style → Charter → Georgia</td><td>paragraphs, blockquotes (default body)</td></tr>
<tr><td><code>--font-display</code></td><td>Fraunces (variable) → Iowan Old Style → Charter → Georgia</td><td>display H1</td></tr>
<tr><td><code>--font-mono</code></td><td>JetBrains Mono → system mono</td><td>H2/H3, UI, labels, code</td></tr>
</tbody></table>

Body sets at **19px / 1.6** for comfortable serif reading. Mono carries the *UI* register; serif carries the *document* register. The mix is the postmodern joke.

**Scale** (modular, raised floor):
`--t-xs 14 · --t-sm 16 · --t-base 18 · --t-md 22 · --t-lg 30 · --t-xl 44 · --t-xxl 68 · --t-mega 112`

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
<span class="badge">v0.5</span>
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

### 3.9 Field (form group)

Wraps a label, control, and optional hint/error in one block.

<div class="field">
  <label for="d-email">Email address</label>
  <input class="input" id="d-email" type="email" placeholder="you@example.com" />
  <span class="hint">We'll only use this to send you the receipt.</span>
</div>

<div class="field">
  <label for="d-bad">Project name</label>
  <input class="input" id="d-bad" value="invalid name!" />
  <span class="error">No special characters allowed.</span>
</div>

```html
<div class="field">
  <label for="x">Label</label>
  <input class="input" id="x" />
  <span class="hint">Help text.</span>
</div>
```

### 3.10 Check & Radio

Square. Native `<input>` styled in place; checked state fills with the accent.

<p>
<label class="check"><input type="checkbox" checked /> ship it on Friday</label><br>
<label class="check"><input type="checkbox" /> ship it on Monday</label><br>
<label class="check"><input type="checkbox" /> skip the all-hands</label>
</p>
<p>
<label class="radio"><input type="radio" name="d-r" checked /> light theme</label>
<label class="radio" style="margin-left:var(--s-4)"><input type="radio" name="d-r" /> dark theme</label>
</p>

```html
<label class="check"><input type="checkbox"> option</label>
<label class="radio"><input type="radio" name="g"> option</label>
```

### 3.11 List

Native `<ul>` and `<ol>` are styled by default. Unordered lists get a short ochre bar in place of a disc; ordered lists get mono numbers with leading zeros.

<div class="grid grid-2 mb-4">
<div>
<ul>
<li>warm newsprint paper</li>
<li>three sober accents</li>
<li>hard shadows, no glow</li>
<li>nested:
  <ul>
    <li>still a bar</li>
    <li>no compounding indent</li>
  </ul>
</li>
</ul>
</div>
<div>
<ol>
<li>read the spec</li>
<li>copy the CSS file</li>
<li>link it in your <code>&lt;head&gt;</code></li>
<li>ship it</li>
</ol>
</div>
</div>

### 3.12 Details (accordion)

Native `<details>` with a plus/minus marker. No JS.

<details>
<summary>What does brutalist mean here?</summary>
<div class="details-body">
It means the structure of the page is the decoration: borders, hard shadows, raw type. Not a 1970s concrete building. Closer to a well-printed manual than a poster.
</div>
</details>

<details open>
<summary>Why no border-radius?</summary>
<div class="details-body">
Round corners blur the edge of every component. Sharp corners read as <em>made of something</em>. Once you start rounding, you have to round everything, and you end up with the same softness as every other system. Hard corners are the cheapest, loudest commitment to a point of view.
</div>
</details>

```html
<details>
  <summary>Heading</summary>
  <div class="details-body">…</div>
</details>
```

### 3.13 Hero

Page-level title block. Big serif headline, lede paragraph, optional meta strip.

<section class="hero">
  <h1 style="font-size:clamp(2.5rem,7vw,5rem)">Concrete pours.</h1>
  <p class="lede">A design system that looks like a document on purpose. One stylesheet, no build step, ten components.</p>
  <p class="meta">v0.5 · maintained by Arrow · MIT-ish, take it</p>
</section>

### 3.14 Footer

A page-bottom strip with mono links and meta, separated by a fat rule.

<footer class="footer">
  <span>© Arrow · 2026</span>
  <span><a href="https://github.com/arrow501/concrete">github</a> · <a href="https://concrete.pages.dev">site</a></span>
</footer>

### 3.15 Pagination

Every page link points to `#top` (or any anchor at the head of the list).
The system enables `scroll-behavior: smooth` globally, so clicking a page glides
the user back to the start of the content. Try it: clicking these scrolls this page to its top.

<nav class="pagination">
  <a href="#top">‹ prev</a>
  <a href="#top">1</a>
  <a href="#top">2</a>
  <span aria-current="page">3</span>
  <a href="#top">4</a>
  <a href="#top">5</a>
  <a href="#top">next ›</a>
</nav>

```html
<!-- somewhere near the top of your page or list -->
<div id="top"></div>

<nav class="pagination">
  <a href="#top">‹ prev</a>
  <a href="#top">1</a>
  <span aria-current="page">2</span>
  <a href="#top">3</a>
  <a href="#top">next ›</a>
</nav>
```

For lists that should anchor mid-page (not the entire viewport), put the
`id="top"` on the list header instead of the page top.

### 3.16 Breadcrumb

<nav class="breadcrumb">
  <a href="#">home</a>
  <a href="#">design</a>
  <a href="#">systems</a>
  <span aria-current="page">concrete</span>
</nav>

### 3.17 Kbd

Press <kbd>⌘</kbd> + <kbd>K</kbd> to open the command palette. Press <kbd>Esc</kbd> to close.

### 3.18 Plate

The unit that gets a figure number. A `.plate` holds an image, an inline
SVG, a canvas, a swatch, or any visual. Discrete widths snap to the grid;
ratio stays natural unless you ask for one. Add a `.plate-tag` for the
corner number, `.plate-pin` for callouts, `.plate-legend` for the key.

**Two photographic plates.** Left: illustration at natural ratio (sets the height). Right: portrait locked to 3:4 — under `.plate-row-match` the second plate stretches to the first's height and its width follows from the ratio.

<div class="plate-row plate-row-match mb-4">
  <div class="plate plate-md">
    <div class="plate-body">
      <img alt="wild rabbit illustration" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Wild_Rabbit_Illustration.png/960px-Wild_Rabbit_Illustration.png" loading="lazy" />
    </div>
    <div class="plate-cap">
      <span class="plate-url"><strong>upload.wikimedia.org</strong><span>/…/Wild_Rabbit_Illustration.png</span></span>
      <a class="plate-dl" href="https://upload.wikimedia.org/wikipedia/commons/2/2f/Wild_Rabbit_Illustration.png" download="rabbit.png">download</a>
    </div>
  </div>
  <div class="plate plate-3x4">
    <div class="plate-body">
      <img alt="rabbit standing on hind legs (LCCN)" src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/Rabbit_standing_on_hind_legs_LCCN2004674687.tiff/lossy-page1-960px-Rabbit_standing_on_hind_legs_LCCN2004674687.tiff.jpg" loading="lazy" />
    </div>
    <div class="plate-cap">
      <span class="plate-url"><strong>upload.wikimedia.org</strong><span>/…/Rabbit_standing_on_hind_legs.jpg</span></span>
      <a class="plate-dl" href="https://upload.wikimedia.org/wikipedia/commons/5/5e/Rabbit_standing_on_hind_legs_LCCN2004674687.tiff" download="rabbit-hind-legs.tiff">download</a>
    </div>
  </div>
</div>

**An SVG diagram with callout pins + legend.** The body hosts an inline
`<svg>`; pins are placed on top with inline `top` / `left`. Same frame, same caption rules.

<div class="plate-row mb-4">
  <div class="plate plate-md">
    <span class="plate-tag">Fig 01</span>
    <div class="plate-body">
      <svg viewBox="0 0 400 280" xmlns="http://www.w3.org/2000/svg">
        <rect width="400" height="280" fill="var(--paper)" />
        <g stroke="var(--ink)" stroke-width="1.5" fill="none">
          <rect x="60" y="60" width="280" height="160" />
          <line x1="60" y1="60" x2="200" y2="20" />
          <line x1="340" y1="60" x2="200" y2="20" />
          <line x1="200" y1="20" x2="200" y2="100" />
          <circle cx="200" cy="140" r="32" />
          <line x1="60" y1="220" x2="340" y2="220" />
        </g>
      </svg>
      <span class="plate-pin" style="top:14%;left:50%">1</span>
      <span class="plate-pin" style="top:50%;left:50%">2</span>
      <span class="plate-pin" style="top:79%;left:20%">3</span>
    </div>
    <div class="plate-cap">
      <span class="plate-url"><strong>concrete.pages.dev</strong><span>/assets/diagram.svg</span></span>
      <a class="plate-dl" href="#" download>download</a>
    </div>
  </div>
  <div class="plate-legend">
<ol>
<li>roof apex — point of pin 1</li>
<li>central node — the bit that does the work</li>
<li>foundation rule — runs the length of the box</li>
</ol>
  </div>
</div>

**A row of small plates.** `.plate-row` wraps on narrow screens; each plate keeps its discrete width.

<div class="plate-row mb-4">
  <div class="plate plate-sm plate-1x1">
    <span class="plate-tag">01</span>
    <div class="plate-body"><div class="plate-swatch" style="background:var(--accent)"></div></div>
    <div class="plate-cap"><span class="plate-url"><strong>--accent</strong><span> · #9a6a14</span></span></div>
  </div>
  <div class="plate plate-sm plate-1x1">
    <span class="plate-tag">02</span>
    <div class="plate-body"><div class="plate-swatch" style="background:var(--link)"></div></div>
    <div class="plate-cap"><span class="plate-url"><strong>--link</strong><span> · #1d4f4a</span></span></div>
  </div>
  <div class="plate plate-sm plate-1x1">
    <span class="plate-tag">03</span>
    <div class="plate-body"><div class="plate-swatch" style="background:var(--alert)"></div></div>
    <div class="plate-cap"><span class="plate-url"><strong>--alert</strong><span> · #7a2a23</span></span></div>
  </div>
</div>

That last row shows the body can hold any element — here it's a flat
`<div class="plate-swatch">` colored by inline style. No image needed.

#### Anatomy

```html
<div class="plate plate-md">
  <span class="plate-tag">Fig 01</span>          <!-- optional corner tag -->
  <div class="plate-body">
    <img alt="…" src="…" />                       <!-- or <svg>, <canvas>, <video>, … -->
    <span class="plate-pin" style="top:30%;left:50%">1</span>
  </div>
  <div class="plate-cap">
    <span class="plate-url">
      <strong>domain.com</strong><span>/path/to/file.jpg</span>
    </span>
    <a class="plate-dl" href="…" download>download</a>
  </div>
</div>
```

#### Modifiers

| class           | effect                                                  |
|-----------------|---------------------------------------------------------|
| `.plate-xs`     | 192 px wide                                             |
| `.plate-sm`     | 256 px wide                                             |
| `.plate-md`     | 384 px wide (default)                                   |
| `.plate-lg`     | 480 px wide                                             |
| `.plate-xl`     | 640 px wide                                             |
| `.plate-1x1`    | force 1:1                                               |
| `.plate-4x3`    | force 4:3                                               |
| `.plate-3x2`    | force 3:2                                               |
| `.plate-16x9`   | force 16:9                                              |
| `.plate-cover`  | with a ratio: crop to fill instead of contain           |
| `.plate-row`    | flex-wrap row of plates                                 |
| `.plate-stack`  | vertical stack of plates                                |
| `.plate-tag`    | corner number/label sitting over the top-left edge      |
| `.plate-pin`    | numbered callout marker (`style="top:…;left:…"`)        |
| `.plate-legend` | numbered key beside a tagged plate                      |

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
- Body is **Spectral at 19px**. Never below 16px for paragraphs.
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

`v0.5`. Renames `.img` → `.plate`: a modular frame for images, SVG drawings,
canvases, swatches. Adds discrete sizes (`xs`/`sm`/`md`/`lg`/`xl`), opt-in
ratios, `.plate-tag` corner labels, `.plate-pin` callout markers,
`.plate-legend` numbered keys, and `.plate-row`/`.plate-stack` composition.

`v0.4`. Adds form fields, check/radio, lists, accordion (`details`),
hero, footer, pagination, breadcrumb, kbd, and figure.
Tokens are stable; component class names will not break in 0.x patches.

`v0.3`. Palette refit to ochre + deep teal + oxblood. Body type Spectral; display Fraunces. Light default; dark opt-in via `.theme-dark`.

<hr class="rule">

<div class="grid grid-2 mt-6 mb-6">
  <div>
    <p class="mono upper muted">end of document</p>
    <p class="serif" style="font-size:var(--t-lg);line-height:1.15">"A building should look like what it is."<br>And so should a website.</p>
  </div>
  <div class="right">
    <span class="stamp">v0.5</span>
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
