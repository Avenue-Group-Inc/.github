---
name: design-system-superhuman
description: Apply the Superhuman-inspired design system when building a landing page, marketing site, dashboard or app screen. Use when the user asks for the "Superhuman" style or design system, or wants a premium, restrained, luxury-minimal look with one purple gesture — Mysteria purple (#1b1938) hero, Lavender Glow (#cbb7fb) as the only accent, Warm Cream (#e9e5dd) buttons, Charcoal Ink (#292827) text, 8px/16px radii only, non-standard 460/540 font weights and 0.96 display line-height. Read DESIGN.md in this folder before writing any UI.
---

# Superhuman-inspired design system

Source: Open Design plugin `design-system-superhuman` v0.1.0 (MIT). The manifest is in `open-design.json`; the full specification is in `DESIGN.md`. **DESIGN.md is the source of truth.** This file only says how to use it.

## Inputs

- **Artifact kind** — `landing page` (default), `marketing site`, `dashboard` or `app screen`.
- **Brief** — what the page should communicate. If it is missing and the conversation does not supply it, ask once.

## Workflow

1. Read `DESIGN.md` in full before writing any markup.
2. Start from the token block below so values match the spec exactly.
3. Build the requested artifact kind using DESIGN.md sections 3–8 (type scale, components, layout, elevation, responsive behaviour).
4. Run the checklist at the end of this file before handing over.
5. Write the file. If the user wants a shareable page, publish it with the Artifact tool. Load `artifact-design` first and follow its rules on font and script sources.

## Token starter

```css
:root {
  /* Colour */
  --mysteria: #1b1938;        /* hero gradient base */
  --lavender: #cbb7fb;        /* the only accent */
  --ink: #292827;             /* text on light; never #000 */
  --amethyst: #714cb6;        /* underlined in-content links */
  --cream: #e9e5dd;           /* primary buttons */
  --parchment: #dcd7d3;       /* card and divider borders */
  --canvas: #ffffff;          /* page background */
  --on-dark: rgba(255, 255, 255, 0.95);
  --on-dark-muted: rgba(255, 255, 255, 0.8);
  --hero-border: rgba(255, 255, 255, 0.2);

  /* Shape: only two radii exist */
  --radius-sm: 8px;           /* buttons, inline elements */
  --radius-lg: 16px;          /* cards, large containers */

  /* Type */
  --font: "Super Sans VF", "Inter", system-ui, -apple-system, "Segoe UI", Roboto,
          Oxygen, Ubuntu, Cantarell, "Fira Sans", "Droid Sans", "Helvetica Neue", sans-serif;
  --w-body: 460;
  --w-display: 540;
  --w-semi: 600;
  --w-bold: 700;
  --lh-display: 0.96;
  --lh-body: 1.5;

  /* Spacing: 8px base */
  --space-1: 4px; --space-2: 8px; --space-3: 12px; --space-4: 16px;
  --space-6: 24px; --space-8: 32px; --space-10: 40px; --space-12: 48px;
}
```

## Fonts

Super Sans VF is proprietary and cannot be loaded, so never link or bundle its files. Keep its name first in the stack (it does no harm), then use a **variable** font so weights 460 and 540 actually render. Inter is the closest open substitute: load it from Google Fonts with the `wght@100..900` axis. With a static font, browsers round 460 to 400 or 500 and the signature texture is lost.

## Brand boundary

This is a style reference. The output carries the user's brand, not Superhuman's:

- Never use the Superhuman name, logo, wordmark, product screenshots or marketing copy in what you build.
- Never build a page that could pass as Superhuman's own site or product.
- Where DESIGN.md calls for product screenshots, use the user's own product UI or neutral placeholders.

## Resolving gaps in DESIGN.md

- **Weights:** the "don't use 400/500/600" rule applies to body and display text. The type table's 500, 600 and 700 for captions, buttons, labels and badges still apply.
- **Nav CTA:** DESIGN.md calls it a "pill", but the system has no pill shapes. Use the 8px radius.
- **Card Heading line-height 0.76:** use it only on single-line titles. If a card title wraps, use the Feature Title value of 1.14.
- **Light vs dark:** the manifest tagline says "premium dark UI", but DESIGN.md documents a white canvas with one purple hero. Follow DESIGN.md as written for landing pages and marketing sites. For dashboards and app screens, or when a dark theme is required (Artifacts need one), map `--canvas`→`--mysteria`, `--ink`→`--on-dark`, `--parchment`→`--hero-border`. Keep the cream buttons and the lavender accent.
- **Status and chart colours:** the system has none. Don't add a second accent hue. For charts, use lavender with ink and parchment tints, and load the `dataviz` skill for chart rules. If a dashboard truly needs error or success states, keep them muted and ask the user before you introduce a new hue.

## Pre-handover checklist

- [ ] Body text weight 460, display weight 540 — not 400 or 500.
- [ ] Display line-height 0.96; body line-height 1.50.
- [ ] Primary buttons are Warm Cream `#e9e5dd` with Ink text and an 8px radius. No pills.
- [ ] Lavender `#cbb7fb` is the only accent hue. No blue, green or red CTAs.
- [ ] Radii are only 8px and 16px.
- [ ] Negative letter-spacing on headlines only; body text stays at 0.
- [ ] Shadows are rare. Depth comes from borders, the hero gradient and product imagery.
- [ ] No text in pure black. Use Ink `#292827`.
- [ ] Mobile: hero around 36px, single column, full-width cream CTAs, 16px side gutters, no horizontal scroll.
- [ ] No Superhuman name, logo, screenshots or copy in the output.
