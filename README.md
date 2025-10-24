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

3. Edit `wrangler.toml`:
   - Set `account_id` to your Cloudflare account id.
   - Optionally change `name` or add `route` for a custom domain.

4. Publish (PowerShell):
   wrangler publish --site . --name cypress-creek-globex-corp

Notes:
- To use the custom domain `cypresscreekglobexcorp.com`, add/verify it in the Cloudflare dashboard and map the site. Cloudflare Pages may be simpler for repo-backed static sites.
- The `wrangler.toml` here is minimal. For Workers or more advanced setups adjust `type`, `main`, and bindings.

