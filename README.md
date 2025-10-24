# Cypress Creek Globex Corperation — Static Site

This is a tiny static landing page that uses `upsacled2.png` as a full-screen background.

Files:
- `index.html` — main page
- `styles.css` — styling
- `upsacled2.png` — background image (already in the repo)
- `wrangler.toml` — Wrangler config (replace placeholders)
- `package.json` — scripts

Quick PowerShell deploy steps (Cloudflare Wrangler)

1. Install Wrangler (if missing):
   npm install -g wrangler

2. Authenticate:
   Option A — browser login:
   wrangler login

   Option B — API token (recommended for CI). Create a token with the needed permissions and then set it in PowerShell for the session:
   $env:CF_API_TOKEN = "YOUR_API_TOKEN"

3. Edit `wrangler.toml` (optional):
   - For Pages deployments, set `pages_build_output_dir = "."` (the repo root) or your build output directory.
   - If deploying a Worker (not this repo), `wrangler deploy` expects a Worker entry-point (main) and bundling settings.

4. Publish (PowerShell) — Pages (preferred for this static site):
   wrangler pages deploy . --commit-dirty=true

Important: `wrangler deploy` is for Workers (JS/TS entrypoints). Use `wrangler pages` for static asset uploads.

Notes:
- To use the custom domain `cypresscreekglobexcorp.com`, add/verify it in the Cloudflare dashboard and map the site. Cloudflare Pages may be simpler for repo-backed static sites.
- The `wrangler.toml` here is minimal. For Workers or more advanced setups adjust `type`, `main`, and bindings.

