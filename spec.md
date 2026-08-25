# Beigale Insights — Landing Page Spec

Status: **built 2026-07-31.** `index.html` implements everything in this spec — Hero, "What We Do," "Who We Work With," "About Beigale," and Contact all match §4 below. Verified in a headless browser at both mobile (390px) and desktop (1440px) widths: no layout overflow, nav (incl. mobile menu) links to the correct anchors, reveal/scroll animations intact.
Source: `Beigale landing site updates.md` (2026-07-31 — repositions Beigale from a single commercial-due-diligence service to two services spanning **pre-deal diligence and post-deal commercial value creation**; restructures the mid-page sections and About accordingly). Prior source: `Beigale_Landing_Page_Dev_Brief_v2.md` (v2, 2026-07-23).
Language: English only, LTR.

> **Note (2026-07-31, biggest revision to date):** This is a strategic repositioning, not a copy tweak — it touches Hero, the main services section, the audience section, About, and the bottom CTA. Summary of structural changes:
> - **Hero** copy replaced (new H1 + H2), positioning both pre- and post-deal work.
> - **Solution (4 pillars)** and **Engagements ("Choose Your Depth", 2 duration-based cards)** are consolidated into one new section, **"What We Do"** — two service cards (Commercial Due Diligence / Post-Deal Commercial Value Creation), reusing the Engagements card's visual style (border-top accent, gold/teal split) but dropping the duration/depth framing entirely. See §4.3 and the open questions below — this consolidation is *inferred* from the brief (which never names "Solution" or "Engagements"), not spelled out, and should be confirmed with Hagai before code work starts.
> - **"Who We've Worked With"** (3-column: Investors / Corporate Acquirers / Deal Advisors + Israel Focus band) is replaced by **"Who We Work With"** (left headline+intro, right two columns: Acquirers / Leadership Teams). Israel Focus band is removed. The "References available upon request" closing line is unchanged (copy and centered/muted styling already match — see §4.4).
> - **"Why Choose Us" / "About Us"** (2026-07-23 naming) is renamed again to **"About Beigale"**, gets a new intro paragraph, and its internal order flips: partner profiles now come **before** the "Why Beigale" credibility grid (previously after). Partner profiles go from a 2-column desktop layout to **stacked vertically at all viewport widths**. "Why Beigale" drops from 5 credibility points to **4**, with new content. A new portrait-oriented joint photo is needed (not yet delivered).
> - **Bottom CTA** headline and button copy both change.
>
> This note supersedes the structural assumptions in the older notes below wherever they conflict; older notes are kept for history.

> **Note (2026-07-31, Tomer's answers to the open questions above):** All 7 open questions raised against this brief are now resolved:
> 1. **Merge confirmed** — there is no more standalone "Engagements" section; "What We Do" uses the Engagements card design.
> 2. **Accent-color mapping** — "exactly like Engagements": same positional mapping as the old cards (first card = gold, second card = teal), so Card 1 (Commercial Due Diligence) = gold, Card 2 (Post-Deal Commercial Value Creation) = teal.
> 3. **Duration/depth framing is fully retired** — "changes completely, it's all in the brief": no ~3 weeks / ~6–8 weeks, no "focused vs. full" anywhere on the page. The brief's card content (§4.3) is the complete, final content.
> 4. **Partner photo** — keep the exact current photo (`assets/partners.png`), no new asset needed; this overrides the brief text's "replace with a new portrait-oriented photo" line. Layout of this part (photo left column / text right column) also stays exactly as currently built.
> 5. **Partner LinkedIn links** — requirement deleted. Do not add LinkedIn links to partner bios.
> 6. **Hero gold emphasis** — none, for now. No word in the new H1/H2 gets the gold treatment.
> 7. **Nav labels** — each anchor link uses that section's eyebrow text as its label.
>
> One follow-up question was also resolved the same day: **"Why Beigale" grid layout at 4 items** — a single row of 4 equal-width blocks, same as the old 4-pillar Solution grid ("like we did in Solution"), not 3+2 or 2×2.
>
> See the relevant subsections below (§4.1–§4.6) and §7, which have been updated to reflect these answers directly rather than flagging them as open.

> **Note (2026-07-31, built):** All of the above is now implemented in `index.html` — see §8 Pending Follow-Up for the shipped checklist.

> **Note (2026-07-17):** This revision removes the standalone "The Gap" section and shortens the Hero subheading. The already-built, client-approved Hero code (see `CLAUDE.md`) still contains the old, longer subheading with the de-emphasized "Financial and legal diligence" phrase — that code has **not** been updated to match this spec yet. **Superseded (2026-07-31):** the Hero subheading target has moved again — see §4.2 below. Do not implement this 2026-07-17 version; go straight to the 2026-07-31 copy.
>
> **Note (2026-07-21):** This revision replaces the old "Who We Serve" section (two-column chip list) with "Who We've Worked With" (editorial three-column layout by client type, plus an "Israel Focus" subsection and a discreet references line — see old §4.5). It also renames the About section's credibility points to "Why Beigale," swaps one point ("Track record" → "Decision-oriented"), and explicitly drops icons from that grid (icons stay pillar-only — see §5 Iconography). Partner bios were reworded and now require a LinkedIn link and a professional (non-circular) portrait per partner. **Superseded in part (2026-07-31):** "Who We've Worked With" itself is now replaced by "Who We Work With" (see above); the LinkedIn-link requirement's status is unclear under the new brief — see Open Questions.
>
> **Note (2026-07-23, brief v2):** Four changes, since superseded/absorbed by the 2026-07-31 revision above except where noted: (1) "About" → "Why Choose Us & Leadership" / "Why Beigale" → "Core Differentiators" — **superseded 2026-07-23 same day** (see CLAUDE.md) by eyebrow "About Us" / h2 "Why Choose Us", and now **superseded again 2026-07-31** by "About Beigale" (§4.5); (2) joint partner photo replacing two individual portraits — **still current**, now additionally required to be portrait-oriented and positioned above the credibility grid, profiles stacked vertically; (3) nav simplified to `Solution · Engagements · Clients · Why Us` + "Contact Us" CTA — **section names this points to no longer exist as such**; nav needs new anchor labels, see Open Questions; (4) Engagements shared callout line — **status unclear**, since the Engagements section itself is being folded into "What We Do," see Open Questions.

---

## 1. Purpose

Credibility page, not a lead-gen funnel. Visitors have already been referred or are pre-vetting Beigale before a first call — a banker, lawyer, or corp-dev lead doing a background check. Success = the page reads as focused, senior, and trustworthy in under a minute. Not optimized for SEO, conversion volume, or cold traffic.

As of the 2026-07-31 brief, that credibility case now spans two moments: **before** the deal (commercial due diligence) and **after** close (commercial value creation) — the page needs to read as one firm credible at both, not two bolted-together offerings.

## 2. Audience

- Corporate acquirers and corp-dev teams
- PE firms and portfolio companies
- VC firms
- M&A lawyers, bankers, transaction advisors (referral sources bringing Beigale into a live deal)
- **New (2026-07-31):** post-close audiences — boards, CEOs, founders/management teams, commercial and go-to-market leaders, and teams leading post-acquisition integration and growth (see §4.4, "Leadership Teams" column)
- Deal geography: Israeli acquirers buying abroad, global acquirers buying Israeli targets, Israeli-to-Israeli deals

All are reading fast, mid-diligence (or mid-integration, post-2026-07-31), and judging competence from tone and structure — not from volume of text.

## 3. Sections

1. Nav
2. Hero
3. What We Do (2 service cards — *replaces the old "Solution" 4-pillar section and "Engagements" duration cards, 2026-07-31*)
4. Who We Work With (*renamed from "Who We've Worked With," restructured, 2026-07-31*)
5. About Beigale (*renamed from "Why Choose Us," reordered, 2026-07-31*)
6. Contact

One-page scroll, anchor-linked nav. No routing/multi-page needed. Section count drops from 7 to 6 with the Solution/Engagements consolidation.

---

## 4. Copy Skeleton

### 4.1 Nav
- Logo (mark): none — text-only "Beigale Insights Ltd." (confirmed 2026-07-15, unchanged)
- Anchor links: **✅ resolved (2026-07-31)** — each link uses its section's eyebrow text as the label: **What We Do · Who We Work With · About Beigale**
- CTA button: "Contact Us" → scrolls to Contact (unchanged from brief v2)

### 4.2 Hero
**H1 (2026-07-31, revised same day):** Commercial diligence and post-deal value creation

**H2 / Subheading (2026-07-31, revised same day):** Independent commercial **assessment** before the deal.[line break]Focused commercial **action** after it. — with "assessment" and "action" in gold (`--hero-accent`); the two sentences are forced onto separate lines with a `<br>`, not left to wrap naturally.

*(This is the second hero copy pass in one day. The first 2026-07-31 pass — H1 "Independent commercial diligence and post-deal value creation," H2 "We help acquirers determine what is commercially real before the deal, and protect, adapt and realize value after close.," no gold — was built, then replaced same-day by Tomer with the copy above, which also reverses the earlier "no gold in hero" answer: gold is back, now on "assessment" and "action" specifically, restoring the pre-2026-07-31 pattern of one bold gold word per line. Both versions are now built in `index.html`'s history — this one is current.)*

### 4.3 What We Do
*(New section name. Consolidates the old 4-pillar "Solution" section and the 2-card "Engagements / Choose Your Depth" section — see the 2026-07-31 note at the top of this file. **✅ Confirmed (2026-07-31):** there is no more standalone "Engagements" section; "What We Do" uses the Engagements card design.)*

**Eyebrow:** WHAT WE DO

**Section headline:** Commercial clarity before the deal.[line break]Commercial progress after it. *(2026-07-31, post-launch, tightened twice: first pass forced a `<br>` after "the deal." with just "the&nbsp;deal."/"after&nbsp;it." nbsp-bound; Tomer then asked for each full sentence on one line with no internal wrap at all — now the entire first sentence and entire second sentence are each fully nbsp-bound. This required lowering the header's mobile font-size floor — see CLAUDE.md — because at the old fixed 1.65rem floor, the unbreakable first sentence didn't fit narrow phone widths and got clipped.)*

**Layout:**
- Two equal-width, equal-height cards, side by side desktop / stacked mobile — same component as the current `.engagement-item` ("Choose Your Depth") cards: same responsive behavior, same border/spacing treatment.
- One accent color per card, reusing the two accent colors already in use on the Engagements cards today. **✅ Resolved (2026-07-31) — "exactly like Engagements":** same positional mapping as the old cards — **Card 1 (Commercial Due Diligence) = gold `--hero-accent`** (first position, same as the old Focused card), **Card 2 (Post-Deal Commercial Value Creation) = teal `--color-accent`** (second position, same as the old Full card).
- Accent applied consistently to the card's icon + one restrained detail (top border or title), same as today.
- One small icon above each card title (2 icons total, down from the current 4 pillar icons): assessment/magnifying-glass/document-check for Card 1, upward-path/execution/acceleration for Card 2. Same icon style and size across both cards.
- Each card: service title, four compact focus areas (bold subhead + one short explanatory line each). No separate descriptor line was ever supplied by the client, so none was added.
- No CTA inside the cards. No additional icons within the cards beyond the one at the top.
- **Subhead sizing (2026-07-31, post-launch tweak):** each focus area's bold subhead (e.g. "Our independent outlook") is deliberately larger than its explanatory line below it (16–17px vs. 13–15px) — the initial build had them backwards (13px fixed subhead, smaller than the body line), fixed same day.

**Card 1 — Commercial Due Diligence**
*(Content is effectively the old 4 Solution pillars, condensed into one card's 4 focus areas.)*

| Subhead | Line |
|---|---|
| What you are really acquiring | The customers, relationships, commercial capabilities and market position underpinning value. |
| How durable it is | Revenue quality, customer concentration and the risks and dependencies that could drive decline. |
| Our independent outlook | Independent bottom-up projections for growth, pricing, margins and EBITDA. |
| The value of combining | Commercial synergy potential and the priorities that matter most after close. |

**Card 2 — Post-Deal Commercial Value Creation**
*(New service line — did not exist in any prior revision of this page.)*

| Subhead | Line |
|---|---|
| Protect what was acquired | Secure critical revenue, customer relationships, people and commercial assets. |
| Address what could undermine value | Resolve the most important commercial risks, dependencies and execution gaps. |
| Adapt the commercial model | Refine positioning, target customers, channels and go-to-market for the new strategic context. |
| Prove the value-creation thesis | Validate growth assumptions, establish repeatable commercial motions and realize synergies. |

**Duration/depth framing: ✅ resolved (2026-07-31) — fully retired.** No ~3 weeks / ~6–8 weeks, no "focused vs. full" choice, anywhere on the page. The card content above is complete and final as given in the brief — nothing about duration gets folded in elsewhere.

### 4.4 Who We Work With
*(Renamed from "Who We've Worked With." Israel Focus is dropped entirely. **Layout revised again 2026-07-31 (post-build):** the two audience groups moved from plain typographic columns to tinted, iconed blocks — see below.)*

**Eyebrow:** WHO WE WORK WITH

**Section headline:** For acquirers and value-creation teams *(shortened 2026-07-31, was "For acquirers and the teams responsible for delivering the value." Renders as one unbroken line at every width — nbsp-bound throughout, with a non-breaking hyphen in "value‑creation" — see CLAUDE.md for why plain hyphens needed special handling too. Trailing period removed 2026-08-01.)*

**Intro:** We support buyers before the deal and leadership teams after close. *(shortened 2026-07-31, was the longer "We work with buyers before the deal and with leadership teams after close, helping them make better commercial decisions and realize the potential of the acquisition.")*

**Layout (revised 2026-07-31, twice):**
- Headline + intro sit full-width at the top of the section (no longer split left/right with the audience blocks beside them).
- Beneath that: two broad **audience blocks**, side by side on desktop, stacked on mobile. Each block has a subtle tinted background, a distinct accent color, a title, and its list.
- **Acquirers block:** teal (`--color-accent`) tint/border.
- **Leadership Teams block:** gold (`--hero-accent`) tint/border — an explicit exception to "gold on dark sections only," matching the same brief-approved treatment already used on the Engagements/What We Do cards. Border/background only — no gold text, to avoid the known gold-on-light contrast issue.
- **Icons removed (2026-07-31, second revision same day):** the blocks briefly had one icon each; Tomer asked to drop them, enlarge the block titles ~20–30% (13px → 16px, still bold/uppercase), tighten the vertical gap the icon used to create, and reduce card padding slightly for a tighter feel. Titles now sit close to the top-left of each card; body-copy list size is unchanged.
- **Israel Focus subsection is removed** (was: Israeli acquirers buying internationally / international acquirers buying Israeli companies / domestic Israeli transactions).

**Audience group 1 — Acquirers** *(condensed 2026-07-31, post-launch)*
- Corporate acquirers and corporate-development teams
- Private equity firms and portfolio companies
- First-time and active buyers
- Family offices

**Audience group 2 — Leadership Teams** *(condensed 2026-07-31, post-launch)*
- Boards, CEOs and founders
- Management and commercial teams
- Teams leading post-acquisition integration and growth

**Closing line, centered beneath the two blocks:** — References available upon request —
*(Styled as a restrained credibility note: smaller than body copy, medium/muted text color, generous spacing above, no button/link/box. Unchanged by the 2026-07-31 layout revision.)*

### 4.5 About Beigale
*(Renamed from "Why Choose Us" / eyebrow "About Us" (2026-07-23) — see CLAUDE.md for the full naming history. Layout instruction from the brief: retain the current section's design and responsive behavior; only the changes below apply.)*

**Eyebrow:** ABOUT BEIGALE

**Section headline:** Senior commercial judgment.[line break]Hands-on support. *(2026-07-31, post-launch: "Senior commercial judgment." is kept unbreakable via `&nbsp;` between its words so it never wraps mid-phrase, and a forced `<br>` puts "Hands-on support." on its own line. This surfaced the same narrow-phone clipping bug as the "What We Do" headline above — fixed with the same lowered mobile font-size floor, see CLAUDE.md.)*

**Intro:** Decades of commercial leadership before and after the deal. *(shortened 2026-07-31, post-launch — was "Beigale brings together decades of commercial leadership, strategy and business-building experience to help acquirers make better decisions before the deal, and help management teams deliver commercial progress after close.")*

**Layout changes from the current build:**
- **Photo: ✅ resolved (2026-07-31) — keep the exact current photo** (`assets/partners.png`), no new asset needed. This overrides the brief text's "replace with a new portrait-oriented photo" line — Tomer confirmed the existing image stays as-is.
- **Photo/text column layout: ✅ resolved — unchanged from the current build.** Photo stays in the left column (same crop treatment: `object-fit: cover`, existing aspect-ratio, no circular crop, no decorative frame), content stays in the right column.
- **Partner profiles move above "Why Beigale"** (previously after it).
- **Partner profiles: ✅ reverted (2026-07-31, later the same day)** — back to side by side on desktop (a horizontal `border-left` divider between them), stacked on mobile only (with the original horizontal `<hr>` divider). The brief text's "stacked at every width" instruction two rows up was tried, then reverted same day — do not re-flatten to always-stacked.
- "Why Beigale" points sit beneath the profiles.
- No new cards, profile boxes, or separate education section.
- **No "The Partners You'll Work With" sub-heading (removed 2026-07-31, post-launch)** — the photo/profiles now flow directly under the section intro paragraph, no label above them.
- Otherwise: keep existing typography, spacing, alignment, and mobile behavior.

**Partner 1 — Hagai Heshes**
*Commercial strategy, positioning and go-to-market*
Hagai has more than 25 years of experience helping technology and healthcare companies sharpen their strategy, positioning and go-to-market. He has held senior marketing and product-marketing leadership roles and works closely with founders, executives and commercial teams on growth, market entry, category creation and commercial transformation. Hagai holds a master's degree from the University of Pennsylvania.

**Partner 2 — Guy Spira**
*Commercial diligence, strategy and business building*
Guy has more than 25 years of experience working with companies, acquirers and leadership teams on commercial strategy, growth and business development. He brings a structured, commercially grounded perspective to assessing businesses, identifying risks and opportunities, and translating strategic priorities into focused action and measurable progress. Guy holds an MBA from Stanford Graduate School of Business.

*(LinkedIn links: ✅ resolved (2026-07-31) — requirement deleted. The 2026-07-21 spec required one per partner; Tomer confirmed that requirement is dropped — do not add LinkedIn links to the bios.)*

**"Why Beigale"** — 4 credibility points (down from 5; entirely new content, not a reshuffle of the old 5):

1. **Independent judgment** — A clear-eyed commercial view, without pressure to validate the deal thesis.
2. **Operators, not just analysts** — Hands-on experience building, positioning and growing businesses, and working alongside management to solve commercial problems. *(em dash → comma, 2026-07-31)*
3. **Candid when it matters** — We say what we believe is commercially true, even when it challenges assumptions or calls for difficult decisions.
4. **Built around the need** — Focused, fast-moving engagements tailored to the specific commercial questions and priorities at hand.

*(Grid layout: ✅ resolved (2026-07-31) — a single row of 4 equal-width blocks, same as the old 4-pillar Solution grid ("What We Do" Card 1's source layout), not a 3+2 or 2×2 split. Collapses the same way the pillar grid did: 2×2 on tablet and mobile too (per the 2026-07-17 pillar-grid decision, see CLAUDE.md).)*

### 4.6 Contact
**Headline:** Before or after the deal, let's talk.

**Primary CTA:** Contact us

**Contact options:** unchanged — email + WhatsApp only, no form. Email `info@beigale.com`, WhatsApp `wa.me/972532851277` (confirmed 2026-07-15).

---

## 5. Design Tokens

### Colors (locked, from brief — unchanged by the 2026-07-31 revision)
| Token | Value | Use |
|---|---|---|
| `color-base` | `#F9F8F5` | Page background, light sections |
| `color-accent` | `#1D9E75` (teal) | Sparse only — links, icon accents, small emphasis marks. Not for large fills. |
| `hero-accent` | `#F0C24B` (gold) | Dark-background sections only; one card accent in "What We Do" per the existing Engagements exception (see CLAUDE.md) |
| `color-dark` | `#2C2C2A` | About Beigale section background (dark contrast section) |
| `color-dark-text` | off-white (`#F9F8F5` or near) | Text on dark section |
| `color-ink` | near-black, derived from `#2C2C2A` or true black | Default body text on light sections |

### Typography
Unchanged — Newsreader (headline/serif), Inter (body/UI), both approved via the hero build.

### Spacing / Layout
- Generous whitespace between sections — page must feel unhurried, not dense.
- "What We Do" is a 2-column grid (collapses to stacked mobile) — reuses the existing Engagements card grid, not the old 4-column pillar grid.
- "Who We Work With" is headline+intro full-width on top, then two tinted audience blocks side by side (stacked on mobile) beneath it — see §4.4.
- Max content width: standard readable measure (~1200px container), text blocks capped narrower (~65ch) for paragraph copy.
- **Inter-section vertical rhythm (2026-07-31, post-launch): every section-to-section gap is a uniform 64px desktop / 32px mobile**, halved from the original 128px/64px target — see CLAUDE.md "Section vertical rhythm halved" for the exact per-section padding values and the reasoning (two padding patterns: standard, and an "elevated top" pattern used by What We Do and About Beigale). Nav anchor scroll-margin was reworked to match (see CLAUDE.md "nav scroll-to-anchor").

### Iconography
- **2 icons** in "What We Do" (one per card — document-check style for Commercial Due Diligence, upward-path style for Post-Deal Value Creation), monochrome, single consistent stroke weight.
- **"Who We Work With" is icon-free again** — the 2 audience-block icons added 2026-07-31 were removed the same day (see CLAUDE.md); the tinted background + accent border still carry the distinct-color identity per block, just without an icon.
- No additional icons inside "What We Do"'s cards beyond the one at the top of each.
- "About Beigale" (credibility grid + partner profiles) and "Who We Work With" are icon-free, card-free (Who We Work With's tinted blocks aren't "cards" in the bordered/boxed sense the DO-NOT list targets, but carry no icon).

---

## 6. Out of Scope

- Lead capture forms (contact is email/WhatsApp link only)
- Blog, resources, or case-study library
- CMS/back-office for content editing (content is static/hardcoded)
- Multi-language / i18n (English only per this spec)
- Analytics beyond basic pageview tracking
- Animations/motion beyond subtle scroll-reveal
- SEO investment (meta tags kept minimal/correct, but not a ranking play)
- Testimonials, logos-of-clients strip, or press mentions — "Who We Work With" names audience *categories* only and closes with "references on request," not displayed
- Circular headshots or decorative photo frames on partner profiles (see §4.5). Partner profiles themselves *are* a 2-column layout on desktop (reverted 2026-07-31, see CLAUDE.md) — stacked only on mobile.

---

## 7. Open Questions

### Answered (2026-07-15 unless noted)
1. **Logo** — ✅ No logo asset. Nav is text-only: "Beigale Insights Ltd."
2. **Contact details** — ✅ Email `info@beigale.com`. WhatsApp link `wa.me/972532851277`.
3. **Typography approval** — ✅ Newsreader/Inter approved via the hero build.
4. **Domain** — ✅ `Beigale.com`.
5. **Gold accent scope** — ✅ Dark-background sections only, plus the one Engagements-card exception (see CLAUDE.md "Lessons Learned").

### Resolved by Tomer, 2026-07-31 (raised against the 2026-07-31 brief, answered same day)
1. **Nav anchor labels** — ✅ each link uses that section's eyebrow text: **What We Do · Who We Work With · About Beigale**.
2. **Accent-color mapping for "What We Do" cards** — ✅ "exactly like Engagements": Card 1 (Commercial Due Diligence) = gold, Card 2 (Post-Deal Commercial Value Creation) = teal (same positions as the old Focused=gold/Full=teal cards).
3. **Engagement duration/depth framing** — ✅ fully retired. "Changes completely, it's all in the brief" — no duration/depth content anywhere on the page.
4. **New portrait-oriented partner photo** — ✅ not needed. Keep the exact current photo (`assets/partners.png`); this overrides the brief's own "new portrait photo" instruction.
5. **Partner LinkedIn links** — ✅ deleted. Requirement dropped; do not add LinkedIn links to bios.
6. **Gold word-emphasis placement in the new Hero subheading** — reversed later the same day (2026-07-31): gold is back, on "assessment" and "action" in the revised H2 (see §4.2). The original "none" answer applied only to the first hero copy pass that day, which was itself replaced.
7. **"Why Beigale" grid layout at 4 items** — ✅ a single row of 4 equal-width blocks, same as the old 4-pillar Solution grid (not 3+2, not 2×2) — collapses 2×2 on tablet/mobile like the pillar grid did.

All 7 open questions from the 2026-07-31 brief are now resolved.

## 8. Pending Follow-Up

**All built, 2026-07-31.** Every item below shipped in `index.html`. The prior "Pending Follow-Up" log (Hero subheading shortening, Gap-section removal, old "Who We've Worked With," old nav copy, old Engagements callout, old "Why Choose Us & Leadership" build, `assets/partners.png` placeholder note, missing LinkedIn URLs, unbuilt Contact section) is superseded by this revision and kept only in the note history above.

- ✅ Hero copy — rebuilt to §4.2, twice same day: first pass had no gold emphasis (old `.hero__sub .commercial` rule removed as dead code); second pass restored gold emphasis via a new `.hero__sub .accent` rule, now on "assessment" and "action." Current H1/H2 match §4.2's revised copy.
- ✅ "What We Do" section — net-new, replaces both the old Solution (`#solution`) and Engagements (`#engagements`) sections/CSS entirely. Card 1 (Commercial Due Diligence) = gold top border, Card 2 (Post-Deal Commercial Value Creation) = teal, per §4.3.
- ✅ "Who We Work With" section (`#who`) — full-width headline+intro on top, then two tinted/iconed audience blocks (Acquirers teal, Leadership Teams gold) side by side desktop / stacked mobile; Israel Focus removed; references line unchanged. Layout revised once more, same day, from the initial plain two-column build to this tinted-block version.
- ✅ "About Beigale" section (`#why`) — renamed, intro paragraph added, partner profiles moved above "Why Beigale" and now stack vertically at every width (photo stays left, same asset/crop), "Why Beigale" rebuilt as a single row of 4 (2×2 on mobile/tablet).
- ✅ Contact section — headline updated to "Before or after the deal, let's talk."; Email Us / WhatsApp Us buttons and contact details unchanged.
- ✅ Nav (desktop + mobile menu) — What We Do · Who We Work With · About Beigale, pointing at `#what-we-do` / `#who` / `#why`; CTA unchanged.
- ✅ `<title>` updated to match the new positioning.

Verified with a headless browser at 390px and 1440px widths: no layout overflow, all anchors resolve, mobile nav toggle works. No remaining open items from this revision.
