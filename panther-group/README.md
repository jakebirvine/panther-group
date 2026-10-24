# Panther Group website

Static site for the Panther Group ARMA MilSim community. Plain HTML/CSS, no build step.

## Files
- `index.html` – the page
- `style.css` – styles (colours are variables at the top of the file)
- `404.html` – "page not found" page (Cloudflare Pages serves it automatically)
- `_headers` – Cloudflare Pages caching and security headers
- `assets/` – unit patches and gallery photos
- `.nojekyll` – only matters for GitHub Pages; harmless on Cloudflare

## Discord link
The invite (`https://discord.gg/MmGKBA5bE6`) is on every element with class `discord-link` in `index.html`, plus the button in `404.html`.

## Deploy to Cloudflare Pages (free, via GitHub)
1. Push this folder's contents to a GitHub repo (e.g. `panther-group`). The files must sit at the repo root, not inside a subfolder.
2. In the Cloudflare dashboard go to **Workers & Pages → Create → Pages → Connect to Git**, authorise GitHub, and pick the repo.
3. Build settings:
   - Production branch: `main`
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: `/`
4. Click **Save and Deploy**. The site goes live at `https://<project-name>.pages.dev`.

Every push to `main` redeploys automatically, and pushes to other branches get their own preview URLs.

### Custom domain (optional)
In the Pages project: **Custom domains → Set up a custom domain**. If the domain's DNS is already on Cloudflare, it's a single click; otherwise Cloudflare shows the CNAME record to add at your registrar.

## Adding a detachment
Copy one `<article class="unit">` block in `index.html`, drop the patch image in `assets/`, and update the text. Add `unit--flip` to the class to put the patch on the right.

## Adding gallery photos
Drop the image in `assets/` and copy one `<figure class="shot">` block in the gallery section. Add `shot--feature` to make a photo the large tile.
