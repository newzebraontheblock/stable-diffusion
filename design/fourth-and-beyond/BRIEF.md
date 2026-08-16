# Fourth & Beyond — website design handoff

Context brief for an AI assistant picking up this work. Pair it with `fb-site.html`
(the mockup file). The HTML shows *what*; this explains *why*, and what is still open.

---

## The business

**Fourth & Beyond** — post-birth home recovery kits for mothers and birth parents,
sold in the UK. The proposition is that the fourth trimester (the ~12 weeks after
birth) is the one nobody prepares you for: all attention goes to the baby, and the
mother's own recovery is overlooked.

Positioning line: *"Nobody prepares you for the fourth trimester. We do."*

Confirmed subhead (use verbatim — do not rewrite):

> Journals and post-birth home recovery care packages, curated by mums and
> perinatal specialists, for body and for mind, beyond the first 42 days.

The phrase **"curated by mums and perinatal specialists"** is the credibility
signal and must survive any edit.

## Product architecture (three parts — all must be visible)

| Part | Role | Notes |
|---|---|---|
| **Home Recovery Kit** | Core physical product | Clinically reviewed; arrives before the due date |
| **Maternal Journal** | Included in every box | Co-created with a midwife and a King's College psychiatrist |
| **Service Vouchers** | Add-on | Physio, counselling, night nanny support |

**Gifting is the primary acquisition mechanic** — the majority of surveyed
respondents prefer to receive a kit as a gift. The page must speak to the
gift-giver directly, not only to the end user.

## Brand system (confirmed — do not substitute)

| Token | Hex | Use |
|---|---|---|
| Deep Green | `#2E3830` | Headers, primary text, dark backgrounds, primary buttons |
| Berry/Coral | `#CC7C72` | Accent details, decorative rules, the `&` in the logo |
| Cream | `#FAF8F4` | Main background |
| Pale Sage | `#E8E8D8` | Secondary/card backgrounds, borders |
| Soft Sky Blue | `#A8C4D8` | Sparing — category tag chips only |

**Typography:** **Alice** for headings, **Calibri** for body. Alice is also the
logo's typeface, so headings and wordmark are deliberately the same face.

- *Alice* is a free Google Font (OFL), so it should be selectable directly in
  Squarespace's font library. It ships a **single regular weight and no italic**
  — every heading is therefore set at 400 and hierarchy is carried by size, not
  weight. Do not set headings bold; it produces a synthesised faux-bold.
- *Calibri* is a Microsoft desktop font. Owning Office does **not** grant web
  use — it needs a separately purchased webfont licence, then upload via
  Squarespace's custom font uploader. *Carlito* is a free, metric-compatible
  substitute if the licence is not worth buying.

Neither face is embedded in the mockup (both were unreachable from the build
environment), so the HTML falls back to whatever the viewing machine has —
most likely Georgia in place of Alice. Layout and spacing are accurate; the
typefaces will substitute.

**Logo:** set in **Alice** — the same face as the headings, which is why Alice
was chosen. Lowercase staggered two-line lockup: "fourth" upper-left, "& beyond"
dropping right beneath it, ampersand leading line two. The mockup reconstructs
this in CSS so it recolours for dark mode and matches the logo's letterforms
once Alice loads. The supplied PNG is black-only; an SVG plus a reversed
(cream) variant is still needed for dark backgrounds and for exact kerning.

## Accessibility deviations from the brand doc — keep these

Measured against WCAG AA. These are deliberate, not errors:

- **Coral buttons fail** (2.96:1 with cream text). Primary buttons are Deep Green
  (11.5:1); coral moved to the hover state.
- **Sky Blue as text fails badly** (1.71:1 on cream). It is used as a *chip
  background* with Deep Green text (6.7:1) for category tags.
- **Coral for small text fails.** A darkened `#AC4B3E` (5.2:1) is used for labels
  and links — same hue (7°) and saturation as the brand coral, just deeper.
  Pure `#CC7C72` is retained for decorative rules and the logo ampersand.

Audience reads this on phones at 3am. Do not restore the failing combinations.

## Page structure

**Home:** hero (H1 + subhead + four-trimester device + inline email capture) →
the gap (problem) → what's inside (three products) → why it's different (three
value props) → gifting → the first 42 days (timeline) → resource hub teaser →
closing CTA.

**Resource Hub:** filterable blog collection. Categories: Recovery / Mental
health / Feeding / Pelvic health / For partners. Each post ends in a waitlist CTA.

Two structural devices carry meaning and should be preserved:

1. **The four-trimester bar** — three faint segments (mapped), the fourth drawn
   in full. States the proposition without a paragraph.
2. **The timeline in days** — Days 1–3 → 4–14 → 15–42 → **Day 43 & beyond**.
   Ties the brand name, the "42 days" subhead and the six-week check to one
   number. "Day 43 and beyond" is the half the company is named after.

## Build constraints

- Platform is **Squarespace 7.1**, built natively in the page editor with
  Custom CSS. Business plan or higher (needed for CSS and code injection).
- **Do not paste the mockup HTML into Squarespace.** It carries its own nav,
  header and footer that will collide with Squarespace's site chrome. It is a
  visual and copy reference only.
- Resource hub should be a native Squarespace **Blog collection** with
  categories, not hand-built pages.
- The mockup's form is inert. The live form must connect to a real backend.

## Open / unresolved

- **Waitlist backend undecided.** Recommendation: Beehiiv or ConvertKit over
  Squarespace's native form, since a blog-fed waitlist needs nurturing over
  months before launch. Not yet chosen.
- **Launch date not set.** A "kits ship [date]" line under the CTA would lift
  conversion; no date confirmed yet.
- **Calibri licensing unresolved.** Needs a purchased webfont licence, or
  substitute the metric-compatible Carlito. Alice is free and unblocked.
- **Logo files.** An SVG and a reversed/cream variant are still needed; only a
  black PNG exists, which fails on Deep Green and in dark mode.

## Do not publish as-is

- **All six resource-hub articles are invented placeholders**, written to be
  plausible for design review. None is clinically reviewed. Nothing there is
  publishable copy.
- **No statistics appear on the page by choice.** The gifting research figure was
  deliberately left off pending a citable sample and date.
- **Photography is unshot.** Image slots are marked as dashed placeholders.
- Any health claim needs clinician sign-off before going live.
