# How to publish this site

This folder contains everything needed to put the family tree online. Pick one of the four paths below.

The site is **unlisted** by default: every HTML file has `<meta name="robots" content="noindex, nofollow">` and there's a `robots.txt` blocking all crawlers. The URL is shareable — search engines just won't pick it up.

---

## Option A — Netlify Drop (easiest, ~30 seconds)

1. Open **https://app.netlify.com/drop** in a browser.
2. Drag this entire `site/` folder onto the drop zone.
3. Wait ~30 seconds. Netlify gives you a random URL like `https://icy-meadow-9842.netlify.app/`.
4. Done. Share that URL with family.

To customize the URL or update the site later:
- Sign up for a free Netlify account (use Google sign-in, takes 30 seconds).
- "Claim" the site you just deployed → it's now in your account.
- Go to **Site settings → Domain → Change site name** to make it `beauchamp-family-tree.netlify.app` or similar.
- To update: drag-and-drop the folder again on the same site dashboard.

---

## Option B — GitHub Pages (~10 minutes, gives you version history)

1. Sign in (or sign up) at **https://github.com**.
2. Create a new repository:
   - Name: `beauchamp-tree`
   - Public ✓
   - Add a README ✓
   - Click "Create repository"
3. Click **"Add file → Upload files"**, drag every file from this `site/` folder, then **"Commit changes"**.
4. Go to **Settings → Pages**:
   - Source: "Deploy from a branch"
   - Branch: `main`, folder: `/ (root)`
   - Save.
5. Wait 2-3 minutes. Your site is at `https://kipgaddis.github.io/beauchamp-tree/`.

To update: drag new files into the repo via the web UI, or use `git push` if you're set up for that.

---

## Option C — Cloudflare Pages (best CDN, ~10 minutes)

1. Sign in (or sign up) at **https://dash.cloudflare.com**.
2. Click **Workers & Pages → Create → Pages → Upload assets**.
3. Project name: `beauchamp-tree`.
4. Drag this `site/` folder into the upload area.
5. Click **Deploy**. Site goes live at `https://beauchamp-tree.pages.dev/`.

To update: same dashboard, "Create new deployment", drag new files.

---

## Option D — Static hosting on a server you already control

Just upload these six files to whatever server's `public_html`/`www` folder:

- `index.html` (this is the front page)
- `beauchamp_panorama.html`
- `beauchamp_summary.html`
- `beauchamp_reference.html`
- `beauchamp_maternal_line.html`
- `robots.txt`

The site is fully self-contained — no server-side code, no databases, no external calls. Anywhere that serves static HTML will work.

---

## Notes

- **File size:** the panorama is ~22 MB because it has every portrait and historical photo embedded as base64 (no external image dependencies). All four free hosts above accept files up to 25 MB without complaint.
- **Privacy:** "unlisted" means search engines won't index it, but anyone with the URL can view it. If you want stricter privacy later (password gate), Netlify and Cloudflare Pages both offer it on paid tiers (~$19/month) — or I can add a simple JavaScript prompt that's free but easily bypassed.
- **Custom domain later:** all four hosts let you swap to a domain like `beauchampfamily.com` later. Just buy the domain at Namecheap or Cloudflare ($10–15/year) and follow the host's "add custom domain" guide.
- **Updates:** when I make changes to the panorama in this session, just re-copy the new HTML files into this `site/` folder and re-deploy.
