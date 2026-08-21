# Recovery Kit Finder — Fourthh & Beyond

A self-contained quiz that recommends one of four routes (Full Recovery Kit,
Services & Journal, Base Recovery Kit, Journal) and drives to a concierge call.

**Everything in `quiz.html` marked `[PLACEHOLDER]` is invented and must be
replaced before this goes near a customer.** Prices, product names, kit
contents, service regions and URLs are all stand-ins so the mechanism could be
built and tested.

## Installing it on Squarespace

1. Edit the page → **Add Block** → **Code**.
2. Paste the entire contents of `quiz.html`. Leave the block's mode as HTML and
   make sure "Display Source" is **unchecked**.
3. Save. Code Blocks need a **Business plan or higher** — they don't exist on
   Personal.

The widget is scoped under `#fb-quiz`, so it can't restyle the rest of your
site, and Squarespace's CSS can't reach into it. It sizes itself to the block,
so put it in a full-width section.

## What to change

Both editable blocks are in the `<script>` tag; search for **`EDIT ME`**.

### 1. `CONFIG`

| Key | What it does |
| --- | --- |
| `bookingUrl` | Your Squarespace Scheduling / Acuity page. **Currently a dead placeholder — the buttons go nowhere until you set this.** |
| `currency` | Symbol used throughout. |
| `serviceRegions` | The places where service vouchers can actually be fulfilled. Anyone picking "Somewhere else" is never shown a voucher route. |
| `emailEndpoint` | Leave `""` and no email capture is rendered. Set it to a form endpoint and an optional "email me this" step appears under the result. |
| `trackEvents` | Fires GA4 events (`quiz_answer`, `quiz_complete`, `quiz_book_call`, `quiz_shop_click`, `quiz_escape_hatch`) if `gtag` is on the page. Harmless if it isn't. |

### 2. `PRODUCTS`

Name, price, product-page URL, blurb and contents for each of the four routes.
`needsServices: true` marks a route as containing vouchers, which is what makes
the location gate work — set it correctly or you'll sell something you can't
fulfil.

### 3. Colours

The palette is CSS variables in the `:root` block at the top of the file. Swap
the hex values for your brand's and nothing else needs touching. Both light and
dark sets are defined; leave the dark block in place or visitors on dark-mode
phones get white-on-white.

## How the recommendation works

Answers add weight to each of the four routes, then two hard filters run before
anything is chosen:

- **Budget** removes routes priced above the band they picked.
- **Location** removes voucher routes if they're outside `serviceRegions`.

Highest remaining score wins; ties break toward the more complete route. If the
filters eliminate everything, it falls back to the cheapest fulfillable option
rather than showing an empty result.

The result page always lists the other three routes with prices, and says *why*
one is unavailable ("Above the budget you set" / "Not available in your area
yet"), so nobody feels funnelled.

## Deliberate decisions worth knowing about

- **No email gate.** The result shows immediately. Gating typically loses
  30–50% of finishers at the last step.
- **An escape hatch on every question** — "I'd rather just talk to someone" —
  goes straight to booking. Some people shouldn't be made to complete a quiz.
- **No celebratory framing.** No "congratulations", no assumption that the baby
  is home or that the pregnancy ended in one. Every timing question has an
  "I'd rather not say" / "I don't know" answer.
- **Answers are never sent anywhere** unless you set `emailEndpoint`. Nothing
  is stored in the browser either.

## Still needed from you

1. Real product names, prices, currency and kit contents — especially **what
   separates the Full kit from the Base kit**, since that difference is what
   question 3 exists to detect.
2. The real service categories and the regions you can fulfil in.
3. Budget bands that match your actual price ladder (the current bands are
   guesses built around the placeholder prices).
4. The Acuity booking URL.
5. Brand hex codes and fonts, and your house vocabulary — "mother" vs "birthing
   parent" vs "new parent" changes a lot of copy in here.
6. Whether birth type (C-section vs vaginal) changes what's in the kit. If it
   does, that's a sixth question; if not, it stays out.
