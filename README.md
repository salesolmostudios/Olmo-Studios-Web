# Olmo Studios — static site

Six self-contained HTML files. No build step, no dependencies, no npm install.

| File | Page |
|---|---|
| `index.html` | Home — hero, preorder form, how it works, plan pricing, chatbots, card pricing |
| `receptionists.html` | AI Voice Receptionists (horizontal scroll) |
| `cards.html` | NFC Review Cards (horizontal scroll) |
| `contact.html` | Contact |
| `privacy.html` | Privacy policy |
| `preorders.html` | Gated preorder list — password `DOGGIFY_OG` |

## Push to GitHub

Drag all six files into your repo at github.com/arnab23das/Olmo-Studios-Final (Add file → Upload files → Commit changes), or with git:

```
cd olmo-studios-site
git init
git add .
git commit -m "Olmo Studios site"
git branch -M main
git remote add origin https://github.com/arnab23das/Olmo-Studios-Final.git
git push -u origin main
```

## Deploy on Cloudflare Pages

1. dash.cloudflare.com → Workers & Pages → Create → Pages → Connect to Git
2. Pick the Olmo-Studios-Final repo
3. Framework preset: None. Build command: blank. Leave build output empty.
4. Save and Deploy

`index.html` is served as the homepage automatically.

## Things to check before it's live

**Preorder form** posts to the Apps Script URL baked into `index.html`. If submissions aren't landing in your sheet, the usual causes are: the Apps Script uses `getActiveSpreadsheet()` instead of `openById('...')`, the sheet tab isn't named exactly `Olmo Studios - Preorders`, or the script was edited without redeploying (Deploy → Manage deployments → pencil → New version → Deploy).

**Admin page** (`preorders.html`) reads the same URL and passes `?key=DOGGIFY_OG`. The password is client-side only — anyone can read it in the page source. Fine for business contacts, not for anything sensitive.

**Preorder counter** on the homepage reads a constant (`PREORDER_COUNT_SEED`, currently 3). To change it, search `index.html` for `PREORDER_COUNT_SEED`.

**Card pricing** is set: $35.99 standard black, $100 for a 10-pack of minis, $100–199 custom engraved metal — all one-time, no monthly.

**The 3–5× reviews figure** is not on the site. If you add a stat, source it.
