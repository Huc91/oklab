# OKLab &amp; OKLCH

A small demo built for the [**Oklab Color Space**](https://www.cssday.it/talk/oklab-color-space/) talk by Luca Ucciero at **CSS Day 2026** (Bologna, 11 June 2026). It walks through three practical things you can do once colors live in the [OKLCH](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/oklch) color space instead of hex/RGB.

> CSS color management is evolving with wider-gamut displays. OKLCH is an intuitive alternative to RGB and HSL: perceived brightness matches the code value, it can express colors conventional formats can't, and `calc()` on its channels yields clearer, more predictable palettes.

## Examples

1. **A plain OKLCH color** — a button styled with `oklch()` and a darker hover, showing the raw syntax: `oklch(lightness chroma hue)`.
2. **Relative color syntax** — derive the hover state from the base color with `oklch(from var(--primary) calc(l - 0.2) c h)`, so you never hand-pick a second value.
3. **A design system from one color** — a full tonal ramp generated with pure `calc()` math, plus three palettes (primary / secondary / neutral) produced by changing only **L**, **C**, or **H** of a single seed color.

The key idea: because OKLCH is perceptually uniform, math on the lightness/chroma/hue channels produces visually even results — unlike the same math in sRGB.

## Running it

It's a static page. Open `index.html` in a browser, or serve the folder:

```sh
npx serve .
```

> **Browser support:** OKLCH is Baseline widely available. The relative color syntax (`oklch(from …)`) used in Examples 2 and 3 needs a recent browser (Chrome/Edge 119+, Safari 16.4+, Firefox 128+).

## Files

| File         | Purpose                                                        |
| ------------ | ------------------------------------------------------------- |
| `index.html` | Semantic markup; each example is a `<section>`.               |
| `style.css`  | All styling, including the OKLCH color work and the ramp math. |

Syntax highlighting in the code blocks is done with [highlight.js](https://highlightjs.org/) loaded from a CDN. Fonts are [Inter](https://fonts.google.com/specimen/Inter) (UI) and [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) (code).
