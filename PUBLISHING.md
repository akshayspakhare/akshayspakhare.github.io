# Publishing this site on GitHub Pages

Everything here is a static site — no build step, no server code. Hash-based
navigation (`#research`, `#tutorials`, …) means GitHub Pages needs no special
configuration.

## Files

- `index.html` — the whole site (489 KB)
- `images/` — the 8 figures, extracted from the draft so the page loads faster
- `.nojekyll` — tells GitHub to serve the files as-is instead of running Jekyll
- `README.md` — what GitHub shows on the repo page
- `LICENSE` — MIT, covering the site code only
- `NOTICE.md` — the real licensing picture: code, prose and publisher figures
  each have different terms
- `.gitignore` — keeps OS cruft and unpublished source material out of the repo

Keep the folder structure intact. `index.html` references `images/fig-01.jpg`
and friends by relative path.

## One-time setup (web browser only, no git needed)

1. Sign in at https://github.com (create a free account if you don't have one).
   Your username becomes part of the URL, so pick it deliberately —
   `akshaypakhare` gives you `akshaypakhare.github.io`.
2. Go to https://github.com/new and create a repository named exactly
   `<your-username>.github.io` (e.g. `akshaypakhare.github.io`).
   Set it to **Public**. Don't add a README.
3. On the empty repo page, click **uploading an existing file**.
4. Drag `index.html`, the `images` folder, and `.nojekyll` into the upload area
   all at once. (If the browser refuses the hidden `.nojekyll` file, skip it —
   it isn't required for this site.)
5. Click **Commit changes**.
6. Wait 1–2 minutes, then open `https://<your-username>.github.io`.

If the repo is named `<username>.github.io`, Pages turns itself on
automatically. If you named it something else (e.g. `website`), go to
**Settings → Pages**, set Source to "Deploy from a branch", branch `main`,
folder `/ (root)`, and the URL becomes
`https://<username>.github.io/website/`.

## Updating the site later

Web UI: open `index.html` in the repo, click the pencil icon, edit, commit.
GitHub redeploys in about a minute.

With git (better once you're editing often):

```bash
git clone https://github.com/<username>/<username>.github.io.git
cd <username>.github.io
# edit files
git add -A
git commit -m "Update research page"
git push
```

## Adding a custom domain later

Nothing here has to change. When you're ready:

1. Buy the domain (Namecheap, Cloudflare Registrar, Porkbun — roughly $10–15/yr).
2. At the registrar, add these DNS records:
   - Four `A` records for `@` → `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`
   - One `CNAME` for `www` → `<username>.github.io`
3. In the repo: **Settings → Pages → Custom domain**, enter the domain, save.
   Tick **Enforce HTTPS** once the certificate is issued (can take an hour).

The `github.io` URL keeps working and redirects to the new domain, so anything
you've already shared stays valid.

## Things worth doing before you circulate the link

- Add a headshot (the site currently has none).
- The dendrite-healing videos: host them as `.mp4` in the repo if each is under
  ~50 MB, otherwise put them on YouTube/Vimeo unlisted and embed. GitHub warns
  above 50 MB per file and hard-blocks at 100 MB.
- Check every DOI link resolves — a few point to 2026 articles.
- Open the site on a phone and walk the nav once.
