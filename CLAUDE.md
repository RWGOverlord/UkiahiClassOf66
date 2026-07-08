# CLAUDE.md — Ukiah High School Class of 1966 Reunion Site

Static reunion website for the Ukiah High School Class of 1966 committee. Built under **Emberforge**. Single-page, hand-off-simple, hosted on GitHub Pages. Audience is ~78 years old — **legibility and simplicity beat everything.**

---

## Roles & workflow
- **Erick (Emberforge)** — owns the architecture and the client relationship. Keeps the project overview in a separate planning thread ("Claude" as architect/advisor). Do not make structural or vendor changes without his sign-off.
- **Claude Code (you, in vscode)** — implementation, tweaks, bug fixes.
- Flag scope creep. This is a fixed-scope one-off. If a change turns "simple static site" into a bigger build, stop and surface it rather than absorbing it.

## Project type & commercial context
- **One-off** contract. The client may want a light refresh for next year's reunion and prefers to stay with Erick, so build for easy reuse, not for a big platform.
- Apply the **"does this make dollars?"** filter: no gold-plating. The value here is a clean, correct, low-maintenance site — not clever engineering.

## Tech & hosting
- **Plain static HTML/CSS**, currently a single file. No framework, no build step, no bundler, no JS dependencies unless truly required. Google Fonts is the only external dependency.
- **Hosting: GitHub Pages** (Erick's standard). Repo lives in Erick's Emberforge GitHub.
- Current deliverable file: `ukiah-class-of-66-mock.html`. For GitHub Pages, this becomes **`index.html`** at repo root.

## Domain
- **Client-owned, Emberforge-operated.** Register with the committee as owner, using **UkiahiClassof66@gmail.com** as the account/registrant email (survives committee turnover). Prepay 2–3 years, auto-renew on. Buy a **bare domain only** — no bundled site subscription.
- Erick connects DNS to GitHub Pages. The prior domain (`ukiahiclassof66.com`) lapsed once already; the whole point is to not let that happen again.

## Payments — SETTLED. Do not change without sign-off.
- **Payments run through Cheddar Up (free tier).** The site does NOT process payments itself.
- The three reserve buttons link OUT to a hosted Cheddar Up collection page.
  - Placeholder URL currently in the markup: `https://cheddarup.com/c/your-collection`
  - **Swap this for the real collection link** once the committee creates their account.
- **Do NOT re-add PayPal or Square branding.** No "Pay with PayPal," no PayPal logo, no PayPal-blue. Those buttons open a Cheddar Up cart; PayPal branding would mislead payers. Buttons use a cart icon and the reunion's purple.

### Why Cheddar Up (so we don't relitigate it)
- **PayPal** was dropped: no real cart, so two different meals became two separate payments. Client wanted one Amazon-style cart with a running total.
- **Square** was evaluated and dropped: 2026 free-tier online rate rose to 3.3% + 30¢, weaker fit for capturing per-guest names, and fund-hold risk on a fresh account taking a sudden burst of payments.
- **Stripe/custom cart** was dropped: overkill for a one-off; adds build + payment liability.
- Cheddar Up fees default to the **payer**, so the committee's cost is ~$0. Standard bank withdrawals are free.

### Cheddar Up collection structure (build sheet, set up separately by committee)
- Free tier allows **5 items / 1 form per page**. Plan uses 4 items:
  1. Dinner — Chicken
  2. Dinner — Beef
  3. Dinner — Vegetarian
  4. Reunion Memory Book
  - (Quilt raffle was **dropped** — do not add it back.)
- Each dinner item gets an **item question**: "Full name of person attending" (open text). This captures meal counts (per item) + attendee names.
- One page-level **form** for purchaser info + **guest/plus-one name** + dietary allergies. The guest-name field is the catch-all for same-meal couples (qty 2 → item question only grabs one name).
- Meal counts come from the Excel export (each meal is its own item), no description-parsing.

## Design system
- **One-page scroll.** The old site was 9 separate GoDaddy pages; we collapsed it to a single scroll with a sticky anchor nav. Do not re-fragment into multiple pages.
- **Accessibility is the point, not a nicety.** Base font 20px, line-height ~1.7, near-black text on warm cream, buttons ≥56px tall with generous padding, single column on mobile. Sections have `scroll-margin-top` so anchor jumps clear the sticky nav.
- **Palette:** Wildcat purple (`--purple #451a6b`) + antique gold accent (`--gold #c2912e`) + cream paper (`--paper #faf6ee`) + near-black ink. **Gold is an accent ONLY — never body/reading text.** (The original site's gold-on-white text was its worst readability problem.)
- **Fonts:** Fraunces (display/headings), Mulish (body), via Google Fonts.
- All colors are CSS variables in `:root`. Reuse them; don't hardcode hexes.

## Page sections (in order)
`nav` → `hero` (school, "1966," 60th Reunion, dates) → `welcome` → `events` (Fri/Sat/Sun schedule) → `reserve` (Reserve & Pay: 2-col card grid, 3 cards) → `hotels` → `photos` → `memory` → `contact` → `footer`.

- **In Memory section:** intentionally a **single warm generic tribute**, NOT a name list. The committee said a full list would be too long. Do not turn it back into a list of names.
- **Reserve section:** 2-column grid, 3 cards — Main event dinner, Reunion memory book, "Can't pay online?" (mail-a-check fallback → scrolls to contact).

## Client requirements (source of truth)
- Amazon-style cart with running totals and a single checkout.
- 3 meal options; capture each attendee's name **including the plus-one's**.
- Simplicity above all — the audience is elderly.
- Bring back the old site's content, refreshed — they didn't like the old *execution*, not the content.

## Open items / placeholders — BLOCKING go-live
Everything below is a placeholder in the markup (look for dashed-outline `.placeholder` spans) awaiting committee input:
- [ ] Reunion **dates** (assumed 60th reunion, 2026 — confirm)
- [ ] Event **schedule** details (Fri/Sat/Sun times + locations)
- [ ] **Dinner price** and **memory book price**
- [ ] Committee **mailing address** (for check payments)
- [ ] Real **Cheddar Up collection URL** (replace placeholder)
- [ ] **Hotels & RV parks** list (names, addresses, phones, room-block codes)
- [ ] **Photos** (committee has them)
- [ ] Confirm **meal names** (assumed Chicken / Beef / Vegetarian)
- [ ] Confirm **school colors** (assumed Wildcat purple/gold)

## Guardrails — do NOT
- Do not add a framework, build step, or backend. Keep it static.
- Do not reintroduce PayPal or Square, or any on-site payment processing.
- Do not lower the accessibility bar (font size, contrast, tap-target size).
- Do not re-fragment the single page into multiple pages.
- Do not use gold as reading text.
- Do not turn the memorial back into a name list.
- Do not re-add the quilt raffle.
