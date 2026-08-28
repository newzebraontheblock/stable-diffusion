# Fourth & Beyond — website update brief

Handoff for the agent working on the site artifact. Apply these changes to the
current build. Copy is written out in full — use it verbatim unless a note says
otherwise.

---

## Context you need

**Fourth & Beyond** — UK postpartum recovery kits, launching spring 2027.
Currently pre-launch: the site's job is waitlist signups, not sales.

**The problem this brief fixes:** the site currently addresses the mother
directly ("nobody prepares *you*"). But most purchases are gifts — friends,
family, colleagues buying for a new mother. A gift-buyer reading the current
page doesn't see themselves in it. Every change below follows from that.

---

## 1. Two buttons in the hero — highest priority

Directly beneath the subhead, above the fold. Do not move them lower.

```
[ Buy for someone else ]     [ Buy for yourself ]
```

- Side by side on desktop, stacked full-width on mobile
- "Buy for someone else" on the left — it's the majority use case
- **Both link to the same waitlist form.** They signal recognition, not
  separate funnels. Two paths get built after launch, not now.
- Primary button style: Deep Green `#2E3830` (coral fails contrast at small
  sizes — keep coral for hover only)

---

## 2. New section — the two paths

Immediately below the hero. Two blocks, side by side on desktop, stacked on
mobile. Equal visual weight — neither is the "real" audience.

**Left block — heading: Buying for someone you love**

> You want to give her something that actually helps. Not another candle. Not
> something she'll smile at and quietly put in a drawer.
>
> Every item is chosen for the things nobody warns her about. It arrives before
> the birth, so it's there when she needs it — not three weeks late, when the
> hardest part has already passed.

**Right block — heading: Buying for yourself**

> You've thought about the pram, the cot, the hospital bag. Almost nobody
> thinks about their own recovery until they're in it.
>
> This is the kit you'd have assembled yourself, if you'd known what to buy and
> had the time to research it.

---

## 3. Product section — convert to accordions

Replace the current dense cards with three collapsed rows. Scanners see three
names instantly; researchers expand for detail.

| Row | Collapsed label | Expanded content |
|---|---|---|
| 1 | **The Home Recovery Kit · £150** | Full contents list |
| 2 | **The Maternal Journal · included in every box** | Created by midwife Laura Godfrey-Isaacs with King's College London |
| 3 | **Service Vouchers · add-on** | Physiotherapy, counselling, night nanny support, ready-made meals |

**Keep the price visible.** Competitors in the premium concierge space hide
pricing because they charge thousands. Showing £150 openly is the
differentiator — do not gate it behind a consultation or enquiry form.

---

## 4. Advisory board section — LEAVE THE SPACE, DON'T WRITE IT

Build the section structure (photo, name, title, one line each) but **do not
write or publish any copy for it yet.**

Reason: the founder is confirming with each advisor how their involvement may
be described. One is an NHS midwife whose conflict-of-interest clearance
depends on not appearing to endorse commercial products. Wording is unresolved
and legally sensitive.

Placeholder only. Await confirmed copy.

---

## 5. Copy on hold — do not use this phrase

The line **"curated by mums and perinatal specialists"** appears in the current
subhead. It is under review and may overstate the advisory board's role — they
advise on what recovery requires; product selection is the founder's.

**Do not propagate this phrase into any new copy.** If a replacement is needed
before the review concludes, use:

> Chosen by a mother. Informed by clinicians.

---

## 6. Smaller copy additions

Two lines, placed where noted:

- **Near the product section:** "Arrives before the due date, ready for the day
  she comes home." *(Timing is the gift-buyer's real anxiety.)*
- **Near the closing CTA:** "Not sure what she needs? Neither is she. That's
  rather the point."
- **Footer:** "Founded by a mother, built with clinicians."

---

## Brand tokens — confirmed, do not substitute

| Token | Hex | Use |
|---|---|---|
| Deep Green | `#2E3830` | Headers, body text, dark backgrounds, primary buttons |
| Berry/Coral | `#CC7C72` | Decorative rules, logo ampersand, button hover |
| Cream | `#FAF8F4` | Main background |
| Pale Sage | `#E8E8D8` | Card backgrounds, borders |
| Soft Sky Blue | `#A8C4D8` | Category tag chips only — never as text |

**Accessibility deviations to preserve:** coral fails WCAG AA on cream at small
sizes. Use `#AC4B3E` for links and small text (same hue, deeper). Sky blue is a
chip *background* with Deep Green text, never text itself. The audience reads
this on phones at 3am — do not restore failing combinations.

---

## Do not publish

- **Resource hub articles** — all current ones are invented placeholders for
  design review. None is clinically reviewed. Not publishable.
- **Statistics** — left off deliberately, pending a citable sample and date.
- **Photography** — unshot. Dashed placeholders are correct for now.
- **Any health claim** — needs clinician sign-off first.

---

## Priority order

1. Hero buttons *(highest value, smallest effort)*
2. Two-paths section
3. Product accordions
4. Small copy additions
5. Advisory board structure — space only, no copy
