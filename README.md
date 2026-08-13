# Olmo Studios — static export

Two self-contained HTML files, no build step, no dependencies:
- `index.html` — the main site
- `preorders.html` — gated preorder list (password: DOGGIFY_OG)

## Push to GitHub

```
cd olmo-studios-site
git init
git add .
git commit -m "Initial commit — Olmo Studios site"
git branch -M main
git remote add origin https://github.com/arnab23das/Olmo-Studios-Final.git
git push -u origin main
```

## Deploy on Cloudflare Pages

1. dash.cloudflare.com → Workers & Pages → Create → Pages → Connect to Git
2. Pick the Olmo-Studios-Final repo
3. Framework preset: None. Build command: blank. Build output directory: /
4. Save and Deploy — live at olmo-studios-final.pages.dev in about a minute

## Before it's real

- Preorder form posts to the PREORDER_ENDPOINT Apps Script URL baked into index.html — confirm that deployment is live (see the original brief's Part 2).
- preorders.html reads the same URL as PREORDER_LIST_ENDPOINT. Admin password is the ADMIN_KEY constant inside preorders.html — client-side only, change it before this goes live for real use.
- Card pricing has placeholder prices — search index.html for the tiers named "Single card", "5-pack", "10-pack", "Custom branded batch".
