# Deploy — your landing page

A single self-contained `index.html` (no build step, no dependencies) plus
`assets/`. Publishes to GitHub Pages in ~2 minutes. Portable to a custom
domain by adding one file.

## Option A — GitHub Pages under the org (free, live immediately)

Canonical URL: **https://humanguardrail.github.io**

1. Create a new **public** repo named exactly `humanguardrail.github.io`
   under the HumanGuardrail org.
2. Push these files to its `main` branch (the whole `gustavo-site/` contents
   at the repo root — `index.html` at top level):
   ```sh
   cd gustavo-site
   git init && git add -A && git commit -m "site: launch"
   git branch -M main
   git remote add origin git@github.com:HumanGuardrail/humanguardrail.github.io.git
   git push -u origin main
   ```
3. Repo → **Settings → Pages** → Source: `Deploy from a branch`, Branch:
   `main` / `/ (root)`. Save. Live at https://humanguardrail.github.io in ~1 min.

## Option B — your own subdomain (recommended once it's up)

You already use `gustavo@humangr.com`, so you likely own `humangr.com`.
To serve the page at `gustavo.humangr.com`:

1. Add a file named `CNAME` (no extension) at the repo root containing one line:
   ```
   gustavo.humangr.com
   ```
2. In your DNS (wherever humangr.com is managed) add a **CNAME record**:
   `gustavo` → `humanguardrail.github.io`.
3. Settings → Pages → Custom domain: `gustavo.humangr.com`, enable
   **Enforce HTTPS** once the cert provisions.

That's the only change — the whole site is domain-agnostic.

## Option C — a personal domain you buy

Same as B: buy `gustavoschneiter.dev` (~$12/yr), put it in `CNAME`, point
DNS at `humanguardrail.github.io`. Best for ranking your own name on Google.

## After it's live — update the canonical URL everywhere

Once you pick the final URL, tell me and I'll swap it into:
- the CV header (currently lists github + linkedin — add the site)
- the LinkedIn Featured section + Contact info → Website
- the org profile README

## Editing later

Everything is in `index.html`. The three demo GIFs and your résumé PDF live
in `assets/`. When you publish the papers, replace the "in preparation" row
in the Writing section with real links — search `paper · <span class="soon">`
in the file.
