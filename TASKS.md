# TASKS — Ukiah High School Class of 1966 Reunion Site

**Rule for Claude Code:** When you finish a task, change its `[ ]` to `[x]`. Never delete a task — check it off so the open list stays visible. Every task has a short **title** and a one-line note. Add new tasks in the same format as they come up.

Status legend: `[ ]` open · `[x]` done. Tasks marked _(committee)_ are Erick/committee actions, not CC's to build.

---

## Content — fill the placeholders
- [x] **Prices and dates** — add the real dinner price, memory book price, and reunion dates (replace the `.placeholder` spans).
- [x] **Event schedule** — add Friday/Saturday/Sunday times and locations. _(Sunday dropped per client. Fri: Ice Breaker 4–10 PM, Ukiah Golf Course Club House. Sat: dinner 4–10 PM, Elks Lodge.)_
- [ ] **Mailing address** — add the committee's check-payment mailing address.
- [x] **Hotels & RV parks** — add names, addresses, phones, and any room-block codes. _(Added 3 hotels + 2 RV parks with addresses, tap-to-call phones, ratings, and "Committee pick" badges. No room-block codes provided — none listed; confirm with committee if any are negotiated.)_
- [ ] **Reunion photos** — add the committee's photos to the photo section.
- [x] **Confirm meal names** — CONFIRMED by 2026 invite: Chicken / Pork / Vegetarian Pasta (was wrongly assumed Beef/Vegetarian). Update the Cheddar Up items to match.
- [x] **Confirm school colors** — CONFIRMED by 2026 invite crest: Wildcat purple/gold.

## Enhancements — UX
- [x] **Responsive mobile nav** — desktop keeps the full link row; mobile gets a slim sticky bar (brand + Reserve + labeled Menu) opening a large slide-down panel. Closes on link/X/outside-tap/Esc; `aria-expanded`, focus management, and reduced-motion handled.

## Payments — Cheddar Up
- [ ] **Create Cheddar Up collection** — _(committee)_ set up the 4 items + item questions + form per the build sheet in CLAUDE.md.
- [x] **Swap in real cart URL** — replace `https://cheddarup.com/c/your-collection` in the markup with the live collection link. _(Both dinner + memory book buttons now point to https://ukiahi-class-of-66.cheddarup.com)_

## Launch — hosting & domain
- [x] **Rename to index.html** — rename `ukiah-class-of-66-mock.html` to `index.html` at repo root so GitHub Pages serves it.
- [x] **Register domain** — _(committee)_ buy bare domain under UkiahiClassof66@gmail.com, prepay 2–3 yrs, auto-renew on.
- [ ] **Connect DNS** — point the domain at GitHub Pages (A/CNAME records) and confirm the site resolves.
- [ ] **Final review pass** — fresh auditor-lens check: all placeholders filled, links work, mobile legibility holds.
