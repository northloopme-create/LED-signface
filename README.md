# Signface — LED Module & Ribbon Population Tool

A single-page tool for tracing a sign photo, auto-populating it with Solan
Modules / First Lites LED modules, and exporting a layout drawing, power
schedule and wiring diagram as a PDF.

Everything lives in **`index.html`** — no build step, no server-side code,
no dependencies to install. It runs entirely in the browser (the only
external resources it loads are a Google Fonts stylesheet and the jsPDF
library, both from public CDNs).

## Publish on GitHub

1. Create a new repository on GitHub (e.g. `signface`).
2. Add these files to it — either by uploading them through the GitHub
   web UI ("Add file → Upload files"), or from the command line:

   ```bash
   git init
   git add index.html render.yaml README.md .gitignore
   git commit -m "Initial commit — Signface LED population tool"
   git branch -M main
   git remote add origin https://github.com/<your-username>/signface.git
   git push -u origin main
   ```

## Deploy on Render

**Option A — one-click from render.yaml (Blueprint)**
1. In the Render dashboard, click **New → Blueprint**.
2. Connect the GitHub repo you just pushed.
3. Render reads `render.yaml` automatically and creates a **Static Site**
   called `signface`. Click **Apply** / **Create**.
4. Render builds and gives you a live URL (`https://signface-xxxx.onrender.com`).

**Option B — manual static site (if you skip render.yaml)**
1. In the Render dashboard, click **New → Static Site**.
2. Connect the GitHub repo.
3. Leave **Build Command** empty.
4. Set **Publish Directory** to `.` (the repo root, since `index.html` sits
   there).
5. Click **Create Static Site**.

Either way, once deployed, every push to `main` automatically redeploys
the site.

## Custom domain (optional)

In the Render dashboard for the site: **Settings → Custom Domains → Add
Custom Domain**, then point your domain's DNS at Render as instructed
on that screen.

## Updating the tool later

Edit `index.html`, commit, and push to `main` — Render redeploys
automatically. There's no database or backend, so there's nothing else
to manage.

## Notes on the data used

Module wattage, voltage and spacing figures for Solan Modules and First
Lites are typical published values for each product family at a given
cross-section depth, used to produce engineering *estimates*. Always
confirm against the current manufacturer datasheet before fabrication.
