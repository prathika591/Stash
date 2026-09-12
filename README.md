# Stash

An expense tracker built for college students living away from home — where money doesn't arrive as a monthly salary, it arrives as an allowance from parents, on whatever schedule that family uses.

**Live demo:** _add your GitHub Pages link here after deploying (see below)_

## Why this is different from a normal expense tracker

Most expense trackers assume you're paid monthly and budget by calendar month. Students don't work that way — you get an allowance every 7, 15, or 30 days (or whatever your family sends), and "how much can I spend today" matters more than "how much did I spend this month." Stash is built around an **allowance cycle** instead of a calendar month:

- Set your allowance amount and how often it arrives.
- The dashboard shows "Safe to spend today" — what's left in the current cycle divided by days remaining — plus "Day 12 of 30 · 18 days left."
- Category budgets and the "committed this cycle" figure are tracked against the same cycle, not the 1st-to-31st calendar month.

## Features

- **Dashboard** — total spent, a daily safe-to-spend number tied to your allowance cycle, and spending broken down by category and account for this month, the full year, or a custom range.
- **Add expense** — full form or one-field quick entry, plus a one-tap "repeat last entry" shortcut.
- **Activity** — every entry, searchable and filterable by category, account, or tag, with inline editing.
- **Tags** — label expenses (e.g. "roommate split," a trip name) and get an automatic total + category breakdown for that label.
- **Allowance & budgets** — set your allowance and cycle length, plus a monthly limit per category with live progress and status.
- **Recurring expenses** — mess fees, WiFi, a shared Netflix subscription — set up once, logged automatically whenever due.
- **Categories built for hostel life** — Hostel & Mess, Tuition & Fees, Books & Stationery, Mobile & Recharge, Outings, Subscriptions, and more, each with a picked icon and color; fully customizable.
- Accounts include UPI alongside Cash, Card, and Bank.
- Fully responsive, with light/dark theme support and a colorblind-aware category palette.

## Tech

Plain HTML, CSS, and JavaScript — no build step, no framework, no dependencies. Data is stored in the browser via `localStorage` when run standalone (as on GitHub Pages); the same codebase also runs inside a Claude artifact, where it transparently syncs through a realtime cloud document store instead.

## Running locally

```bash
git clone https://github.com/<your-username>/stash.git
cd stash
python3 -m http.server 8000
# open http://localhost:8000
```

Or just open `index.html` directly in a browser.

## Deploying (for a public link)

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to "Deploy from a branch," branch `main`, folder `/ (root)`.
4. Save — GitHub gives you a live URL at `https://<your-username>.github.io/stash/` within a minute or two.

## Installing it as an app

Stash is a Progressive Web App (PWA) — once it's deployed (e.g. on GitHub Pages, which serves it over HTTPS), it can be installed to a home screen or desktop like a real app, with its own icon and no browser address bar:

- **Android (Chrome):** open the live link, tap the **⋮** menu, then **Add to Home screen** / **Install app**.
- **iPhone/iPad (Safari):** open the live link, tap the **Share** button, then **Add to Home Screen**.
- **Desktop (Chrome/Edge):** open the live link, click the **install** icon (⊕ or a small monitor icon) at the right side of the address bar.

Remember: when uploading the `icons` folder to GitHub, drag the whole folder in (not the two image files individually) so it keeps its `icons/` path — otherwise the app icon won't show up correctly.

It also works offline after the first visit, since a service worker caches the app shell.

## License

MIT
