# makeupcounter-live

A single-page web app for tallying how many times you use each product.

Open `index.html` in a browser — that's the whole app. No server, no build step,
no dependencies. Everything is stored in your browser's `localStorage`, so
nothing is uploaded anywhere.

## What it does

- **Tally a use** — one tap on `+1` per use, `−` to correct a miscount, and an
  **Undo** toast for the last tap.
- **Groups** — organize products into groups (starts with Face, Eyes, Lips,
  Skincare) and filter by group with the tabs, or see everything under **All**.
- **Default group** — starred in the tabs. The app opens on it, and it's the
  group preselected in the add form when you're on the **All** tab. Change it in
  **⚙ Settings → Default group**, or in **Groups → Make default**.
- **Time ranges** — see counts for today, the last 7 days, the last 30 days, or
  all time. Products sort most-used-first for whichever range you pick.
- **Manage** — rename products, move them between groups, or delete them via the
  `⋯` button. Rename, add, and delete groups in the **Groups** dialog; deleting a
  group moves its products to another group rather than losing their counts.
- **Export / import** — download your data as JSON and load it back on another
  device or browser.

## How counts are stored

Each product keeps a per-day tally (`{"2026-08-16": 3}`), so the day/week/month
views are derived from real history rather than a single running total. Days
roll over automatically at local midnight, even if you leave the app open.

## Hosting it

Because it's one static file, GitHub Pages can serve it as-is: **Settings →
Pages → Deploy from a branch → `main` / `/ (root)`**. Once it's live you can add
it to your phone's home screen and it behaves like an app.
