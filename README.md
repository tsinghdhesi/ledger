# Ledger — hosting on GitHub Pages

## 1. Push these files to a GitHub repo
Create a new repo (e.g. `ledger`), and add these files to the **root**:
- `index.html`
- `manifest.json`
- `sw.js`
- `icon-192.png`
- `icon-512.png`

```bash
git init
git add .
git commit -m "Add ledger app"
git branch -M main
git remote add origin https://github.com/<your-username>/ledger.git
git push -u origin main
```

## 2. Enable GitHub Pages
In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main, folder: / (root) → Save**.

Your site will be live at:
`https://<your-username>.github.io/ledger/`

(Takes ~1 minute to go live after enabling.)

## 3. Add it to your phone's home screen
- **iOS (Safari)**: open the URL → Share icon → "Add to Home Screen"
- **Android (Chrome)**: open the URL → menu (⋮) → "Install app" or "Add to Home screen"

You'll get a real app icon that opens full-screen, no browser chrome.

## Important — read this
Data is stored in **`localStorage`**, scoped to that exact URL, in that specific browser/app.
This means:
- Data on your phone and data on your laptop are **separate** — they will not sync. Logging a purchase on your phone won't show up if you open the site on your laptop, and vice versa.
- If you clear Safari/Chrome site data, or use a private/incognito window, your data disappears.
- **Back up regularly** using the ↓ (download) button in the app — it saves everything as a single `ledger-backup.json`. On desktop Chrome/Edge it overwrites that same file each time (you pick where once, then it's a silent one-click save); on iPhone/Safari it downloads under that fixed name — if a copy piles up in Downloads, it's safe to delete older ones, only the newest matters. Use the ↑ (upload) button to restore it, on the same device or a different one.

If down the line you want actual cross-device sync, that requires a small free backend (e.g. Firebase or Supabase) — happy to build that version whenever you want it.
