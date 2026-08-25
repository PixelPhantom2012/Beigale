---
name: Beigale Insights
description: Credibility-only one-pager for a boutique M&A commercial due diligence firm
colors:
  base: "#F9F8F5"
  accent: "#1D9E75"
  dark: "#2C2C2A"
  dark-text: "#F9F8F5"
  ink: "#2C2C2A"
  hero-bg: "#211F1A"
  hero-text: "#F9F8F5"
  hero-accent: "#F0C24B"
typography:
  display:
    fontFamily: "Newsreader, serif"
    fontSize: "clamp(1.9rem, 7vw, 3.625rem)"
    fontWeight: 400
    lineHeight: 1.14
    letterSpacing: "-0.01em"
  headline:
    fontFamily: "Newsreader, serif"
    fontSize: "clamp(1.65rem, 6vw, 2.75rem)"
    fontWeight: 400
    lineHeight: 1.2
    letterSpacing: "-0.01em"
  title:
    fontFamily: "Inter, sans-serif"
    fontSize: "clamp(0.9375rem, 3.6vw, 1.0625rem)"
    fontWeight: 600
    lineHeight: 1.35
  body:
    fontFamily: "Inter, sans-serif"
    fontSize: "clamp(1.05rem, 3.5vw, 1.375rem)"
    fontWeight: 400
    lineHeight: 1.6
  label:
    fontFamily: "Inter, sans-serif"
    fontSize: "13px"
    fontWeight: 600
    lineHeight: 1.4
    letterSpacing: "0.08em"
rounded:
  sm: "2px"
spacing:
  space-2: "16px"
  space-3: "24px"
  space-4: "32px"
  space-5: "48px"
  space-6: "64px"
  space-7: "96px"
  space-8: "128px"
components:
  button-primary:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.sm}"
    padding: "9px 16px"
  button-primary-hover:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.base}"
  pillar-icon:
    textColor: "{colors.accent}"
    size: "32px"
---

# Design System: Beigale Insights

## 1. Overview

**Creative North Star: "The Closing Binder"**

Beigale Insights reads like the tabbed, precisely-assembled binder handed across the table at a deal's close: paper-white pages, one serif headline per section, everything else set in a quiet, structured sans. Nothing is decorative because nothing needs to persuade through decoration — the firm's confidence comes from the operators, not from the interface. The system is built for a reader who is mid-diligence, skimming fast, and judging seniority from restraint rather than volume.

It explicitly rejects SaaS visual grammar: no gradient hero metrics, no filled icon sets, no card-grid sameness, no motion for its own sake. The only departure from flat paper-white is two deliberately scoped dark sections (Hero, About) that mark identity shifts, not decoration.

**Key Characteristics:**
- Paper-flat: no shadows, no elevation, depth comes from background contrast and whitespace only
- One serif voice (Newsreader) reserved strictly for headlines; everything else is Inter
- Two accent colors, each locked to a background: teal on light, gold on dark, never mixed
- Generous, 8px-based rhythm; short lines everywhere, nothing reads as a text block

## 2. Colors

A near-monochrome paper palette carries the page; teal and gold are rationed to single words, icons, and labels.

### Primary
- **Ledger Teal** (`#1D9E75`): the light-section accent. Section eyebrow labels ("Solution", "Engagements"), pillar icons, link hover, focus rings. Never a fill, never on a dark background.

### Secondary
- **Signature Gold** (`#F0C24B`): the dark-section accent, used only inside Hero and About. Word-level emphasis only (e.g. "commercial" in the hero subhead), always `font-weight: 600`. Measures ~1.6:1 against Warm Paper White, so it is never used on a light background.

### Neutral
- **Warm Paper White** (`#F9F8F5`): page background and text-on-dark. The base surface for every section except Hero and About.
- **Boardroom Charcoal** (`#2C2C2A`): the About section background, and (as `--color-ink`) the default body-text color on light sections.
- **Near-Black Oak** (`#211F1A`): the Hero's own, slightly deeper background — bespoke to Hero, not reused elsewhere.

### Named Rules
**The Background-Locks-the-Accent Rule.** Teal appears only on Warm Paper White sections; gold appears only on Boardroom Charcoal / Near-Black Oak sections. Swapping either breaks contrast and breaks the rule simultaneously — there is no scenario where they cross.

**The Sparse-Accent Rule.** Both accents are used for icons, eyebrow labels, links, and single-word emphasis. Neither is ever a background, a button fill, or a large shape.

## 3. Typography

**Display / Headline Font:** Newsreader (serif), with Georgia/serif fallback
**Body / UI Font:** Inter (sans), with system-sans fallback

**Character:** An editorial serif for moments of statement (H1, section headers) paired with a neutral, highly-legible sans for everything a fast-reading, mid-diligence audience actually has to parse.

### Hierarchy
- **Display** (400, `clamp(1.9rem, 7vw, 3.625rem)`, 1.14): Hero H1 only. The single largest statement on the page.
- **Headline** (400, `clamp(1.65rem, 6vw, 2.75rem)`, 1.2): Section headers (e.g. "Confirming the deal is worth it."), max-width 18ch.
- **Title** (600, `clamp(0.9375rem, 3.6vw, 1.0625rem)`, 1.35): Card/pillar-level sub-headlines (pillar headlines, engagement titles). Inter, not Newsreader — Newsreader is reserved for the two headline tiers above.
- **Body** (400, `clamp(1.05rem, 3.5vw, 1.375rem)`, 1.6): Hero subhead and section intros; paragraph copy capped at 58–65ch.
- **Label** (600, 13px, 1.4, tracking `0.08em`, uppercase): Eyebrow section labels and the engagement duration tag.

### Named Rules
**The One-Serif Rule.** Newsreader appears only at Display and Headline tier. Every other piece of type on the page, including pillar and card headlines, is Inter. Mixing the serif into body or label tiers is prohibited.

## 4. Elevation

Flat by design: there is no `box-shadow` anywhere in the system. Depth is conveyed by background contrast (Warm Paper White sections against the two dark sections) and by generous whitespace between blocks, not by lifting elements off the page.

### Named Rules
**The No-Shadow Rule.** Nothing in this system casts a shadow. Separation between elements comes from whitespace, background contrast, and hairline 1px borders (`rgba(44,44,42,0.06–0.3)`), never elevation.

## 5. Components

### Buttons
- **Shape:** Near-square, 2px radius (`rounded.sm`) — deliberately not soft or pill-shaped.
- **Primary (nav CTA):** Transparent background, 1px border `rgba(44,44,42,0.3)`, ink text, `9px 16px` padding (desktop `11px 22px`). Reads as a quiet outline, not a filled call-to-action.
- **Hover / Focus:** Hover inverts to solid ink background with Warm Paper White text (`background 0.15s ease, color 0.15s ease`). Focus-visible gets a 2px Ledger Teal outline, 2px offset, 2px radius — the only place teal appears as an outline rather than a fill/icon.

### Icons (Pillars)
- **Style:** Single-color line icons, 1.5px stroke, round line caps/joins, no fill. 24–32px (`clamp(24px, 6vw, 32px)`), colored in Ledger Teal.
- **Rule:** One icon per pillar, consistent stroke weight across the set. Never mix filled and line icons.

### Navigation
- **Style:** Sticky top bar, Warm Paper White background, 1px hairline bottom border (`rgba(44,44,42,0.08)`). Logo set in Newsreader 500; links in 14px Inter at 65% ink opacity, full ink on hover.
- **Mobile:** Collapses to a 44px hamburger toggle; the mobile menu is a sticky, full-width stack of 44px-min-height link rows with hairline dividers, not an overlay or drawer.

### Cards / Containers
This system deliberately has none. Pillars, engagement items, and credibility points sit directly on the section background with no card shell, no border, no shadow — only icon/label + heading + list, separated by the grid's own gap.

## 6. Do's and Don'ts

### Do:
- **Do** lock Ledger Teal (`#1D9E75`) to light (Warm Paper White) sections and Signature Gold (`#F0C24B`) to dark (Near-Black Oak / Boardroom Charcoal) sections, never crossed.
- **Do** reserve Newsreader for Display and Headline tiers only; everything else is Inter.
- **Do** cap paragraph copy at 58–65ch and keep every section scannable — short lines and short lists, never dense blocks.
- **Do** use the project's 8px-based spacing scale (16 / 24 / 32 / 48 / 64 / 96 / 128) for all vertical rhythm.
- **Do** keep the two dark-background sections limited to Hero and About; every other section stays on Warm Paper White.

### Don't:
- **Don't** use teal or gold as a background fill, button fill, or large shape — sparse accents only (icons, labels, single-word emphasis).
- **Don't** put Signature Gold on a light background — it measures ~1.6:1 against Warm Paper White and is unreadable there.
- **Don't** add a lead-capture form; contact is email + WhatsApp link only.
- **Don't** add shadows, gradients, gradient text, or glassmorphism anywhere — this system is flat by design.
- **Don't** use decorative or filled icon sets; line icons only, one per pillar/credibility point, consistent stroke weight.
- **Don't** wrap pillars, engagements, or credibility points in card shells — this system has no card component.
- **Don't** add motion beyond the existing rise-in and scroll-reveal transitions; nothing decorative, nothing looping.
