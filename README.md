# Sajjad Ahamed — Academic Website

A minimal, dependency-free academic website (4 pages, plain HTML/CSS). No build
step, no framework, nothing to maintain. Edit the HTML files directly in any
text editor — each page is fully self-contained.

## Files

- `index.html` — Home (headshot + bio + contact)
- `research.html` — Publications, working papers, policy writing
- `teaching.html` — Courses taught
- `cv.html` — CV download page
- `assets/headshot.jpg` — PLACEHOLDER — replace with your real headshot (keep the same filename)
- `assets/cv.pdf` — MISSING — add your CV PDF here with this exact filename

## Before publishing — edit checklist

1. **index.html**: replace the email address and LinkedIn URL (search for "TODO").
2. **research.html**: replace every [bracketed placeholder] with exact,
   verified titles, years, co-authors, and links. Verify the JCCA DOI resolves.
3. **teaching.html**: fill in [Semesters] for each course.
4. **cv.html**: add `assets/cv.pdf` and set the "Last updated" date.
5. **assets/headshot.jpg**: replace with a real headshot (portrait orientation,
   roughly 900×1100px, under 500KB).

## Deploy to GitHub Pages (free)

1. Create a GitHub account if you don't have one.
2. Create a new **public** repository named exactly:
   `YOUR-USERNAME.github.io`
3. Upload all files from this folder (keep the `assets/` subfolder structure):
   on the repo page, "Add file" → "Upload files" → drag everything in → Commit.
4. Wait 1–2 minutes. Your site is live at `https://YOUR-USERNAME.github.io`.

That's it. To update the site later, edit a file on GitHub (pencil icon) and
commit — changes go live within a minute or two.

## Custom domain (recommended, ~$10/year)

1. Buy a domain (e.g., sajjadahamed.com) at Cloudflare Registrar or Namecheap.
2. In your repo: Settings → Pages → Custom domain → enter your domain → Save.
3. At your registrar, add these DNS records:
   - Four `A` records for the apex domain (`@`) pointing to GitHub Pages'
     IP addresses (listed in GitHub's official Pages documentation — check
     the current values there, as they can change)
   - One `CNAME` record for `www` pointing to `YOUR-USERNAME.github.io`
4. Back in GitHub Pages settings, tick "Enforce HTTPS" once available
   (can take up to 24 hours after DNS propagates).

## Maintenance rule

Update the site every time something changes (new publication, new semester,
new CV) and at minimum once per semester. A stale site is worse than no site.
