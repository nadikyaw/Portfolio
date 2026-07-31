# Nadi Kyaw — Portfolio Site

A single-page portfolio site. No build step, no dependencies — just static files.

## Files

- `index.html` — the whole site (markup, styles, and a tiny script for the footer year)
- `assets/favicon.svg` — browser tab icon (navy "NK" monogram)
- `robots.txt` / `sitemap.xml` — search engine crawling config
- `.nojekyll` — tells GitHub Pages to serve files as-is

## Before you go live

Two placeholders need your real domain once you have one — search each file for `example.com` and replace it:

- `index.html` — `<link rel="canonical">` and the Open Graph/Twitter `og:url` tags
- `robots.txt` — the `Sitemap:` line
- `sitemap.xml` — the `<loc>` value

Optional: `og:image` in `index.html` points to `/assets/og-image.png`, which doesn't exist yet. Add a 1200×630px preview image at that path (or remove the tag) so links you share show a nice card on social media / iMessage / Slack.

## Deploying

Pick whichever fits your domain plans.

### Option A — GitHub Pages (free, uses your existing GitHub account)

1. Push this folder to a new GitHub repo (e.g. `nadikyaw/portfolio`, or `nadikyaw.github.io` for a URL with no extra path).
2. In the repo: **Settings → Pages → Source → Deploy from a branch**, pick `main` and `/ (root)`.
3. Your site is live at `https://<username>.github.io/<repo>/` (or just `https://<username>.github.io/` if you used the special repo name above).
4. Custom domain later: add a `CNAME` file at the repo root containing your domain, then point your domain's DNS at GitHub Pages (Settings → Pages shows the exact records to add).

### Option B — Netlify or Vercel (free, easiest custom domains)

1. Drag this folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or connect the GitHub repo for auto-deploys on every push.
2. Add your custom domain under the project's domain settings — both platforms issue free HTTPS certificates automatically.

### Option C — Any static host

These are just plain files. Any host that serves static files (Cloudflare Pages, S3 + CloudFront, a shared host, etc.) works — upload the contents of this folder to the web root.

## Editing later

Everything — content, colors, layout — lives in `index.html`. Colors are defined once at the top of the `<style>` block under `:root` if you want to retheme.
