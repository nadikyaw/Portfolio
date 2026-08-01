# Deployment Guide

This site is deployed with **GitHub Pages**, directly from the `main` branch of this repository. Live URL:

**https://nadikyaw.github.io/Portfolio/**

## First-time setup

1. Push your code to the `main` branch on GitHub (already done if you're reading this from the repo).
2. Go to your repository on GitHub: `https://github.com/nadikyaw/Portfolio`
3. Click **Settings** (top navigation of the repo).
4. In the left sidebar, click **Pages**.
5. Under **Build and deployment** → **Source**, select **Deploy from a branch**.
6. Under **Branch**, select `main` and folder `/ (root)`, then click **Save**.
7. Wait 1–2 minutes for the first deployment to finish. GitHub will show a green banner with your live URL once it's ready.
8. Visit **https://nadikyaw.github.io/Portfolio/** to confirm it's live.

> Note: the site lives at `nadikyaw.github.io/Portfolio/` (with the `/Portfolio/` path) because the repository is named `Portfolio`, not `nadikyaw.github.io`. Only a repo named exactly `<username>.github.io` gets served at the bare root domain.

## Making updates after deployment

Deploying is not a one-time action — every push to `main` automatically republishes the site. There's no separate "finalize" or "lock" step.

```bash
# 1. Make your edits (e.g. index.html)

# 2. Stage and commit
git add index.html
git commit -m "Describe what changed"

# 3. Push to main
git push origin main
```

GitHub Pages rebuilds automatically after each push — the live site usually updates within 1–2 minutes. You can check build status under the repo's **Actions** tab if it doesn't appear to update.

## Checking deployment status

- Repo → **Actions** tab: shows the "pages build and deployment" workflow run and whether it succeeded or failed.
- Repo → **Settings → Pages**: shows the current live URL and last deployment time.

## Files relevant to deployment

| File | Purpose |
|---|---|
| `index.html` | The site itself |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing and serve files as-is (required since this is a plain HTML/CSS/JS site, not a Jekyll project) |
| `robots.txt` | Search engine crawler rules |
| `sitemap.xml` | Search engine sitemap, points to the live URL |
| `assets/` | Images, favicon, and the downloadable CV PDF |

## Rolling back a bad deploy

If a pushed change breaks something:

```bash
# Find the commit hash you want to revert to
git log --oneline

# Revert the most recent commit (creates a new commit undoing it)
git revert HEAD
git push origin main
```

This is safer than `git reset --hard` since it preserves history instead of discarding it.

## Taking the site offline

Go to **Settings → Pages** and set **Source** back to "None." This unpublishes the site but does not delete any files or history in the repository — it can be re-enabled anytime by repeating the first-time setup steps above.
