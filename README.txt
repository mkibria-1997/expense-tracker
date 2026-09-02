# Ledger — Personal Expense Tracker

A self-contained expense tracker: category breakdowns, a spending chart, and
weekly/monthly filtering. All data is stored only on your phone (in the
browser's local storage) — nothing is sent anywhere.

## Install it on your Android phone

Opening the HTML file directly (`file://`) works for basic use, but Android
Chrome only offers the **full "Install app"** experience (no address bar,
offline caching) when the files are served over `https://`. The easiest free
way to do that:

### Option A — Netlify Drop (no account, 2 minutes)
1. On your computer, go to **https://app.netlify.com/drop**
2. Drag the whole `expense-tracker` folder onto the page.
3. Netlify gives you a link like `https://random-name.netlify.app`.
4. Open that link on your Android phone in Chrome.
5. Tap the **⋮** menu → **"Add to Home screen"** (or use the **Install app**
   banner that appears at the bottom of the page).
6. The Ledger icon now sits on your home screen and opens full-screen, like a
   normal app.

### Option B — GitHub Pages (if you already use GitHub)
1. Create a new repo and upload the contents of the `expense-tracker` folder.
2. In the repo, go to **Settings → Pages**, set the source to the main
   branch, save.
3. Visit the `https://<yourusername>.github.io/<repo>/` URL on your phone and
   follow steps 5–6 above.

### Option C — Quick local test (no hosting)
Just open `index.html` directly in Chrome on your phone (e.g. by uploading it
to Google Drive and opening it, or sharing it to yourself). This works
immediately for adding/viewing expenses, but skip Options A/B when you're
ready for the full home-screen app experience.

## Files
- `index.html` — the whole app (structure, style, logic)
- `manifest.json` — tells Android this is an installable app
- `service-worker.js` — caches the app so it still opens without internet
- `icon-192.png`, `icon-512.png` — home screen icons

## Notes
- Data lives in your phone's browser storage. Clearing Chrome's site data for
  this app will erase your transactions — there's no cloud backup built in.
- Currency is set to USD ($). If you ever want a different currency or
  additional categories, those are easy to change in `index.html` near the
  top of the `<script>` section (`CATEGORIES` / `INCOME_CATEGORIES`).
