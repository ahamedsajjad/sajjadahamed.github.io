# Deploying to www.sajjadahamed.com

Follow these in order. Total hands-on time: ~30 minutes, plus waiting for DNS.

---

## Step 0 — Buy the domain (do this first)

Register `sajjadahamed.com` at **Cloudflare Registrar** or **Namecheap** (~$10-12/yr).
Enable free WHOIS privacy at checkout.

Note: you buy the APEX domain `sajjadahamed.com`. The `www.` part is a
subdomain you configure yourself — it is not sold separately.

---

## Step 1 — Create a GitHub account

Go to github.com and sign up. Choose your username carefully — it becomes a
public part of your professional identity and appears in your backup URL.
Suggested: `sajjadahamed`.

---

## Step 2 — Create the repository

1. Click the **+** (top right) → **New repository**
2. Repository name: `YOUR-USERNAME.github.io`
   (exact — if your username is `sajjadahamed`, the repo is `sajjadahamed.github.io`)
3. Visibility: **Public** (required for free GitHub Pages)
4. Do NOT tick "Add a README file"
5. Click **Create repository**

---

## Step 3 — Upload the site files

1. On the empty repo page, click **uploading an existing file**
2. Unzip the site folder on your computer, then drag in ALL of these:
   - `index.html`, `research.html`, `teaching.html`, `media.html`, `cv.html`
   - the whole `assets/` folder (keep it as a folder)
   - `CNAME`  ← important, already set to www.sajjadahamed.com
   - `.nojekyll`
3. Scroll down, click **Commit changes**

Note: `CNAME` and `.nojekyll` may be hidden on your computer.
- Mac: press `Cmd + Shift + .` in Finder to show hidden files
- Windows: File Explorer → View → tick "Hidden items"

---

## Step 4 — Turn on GitHub Pages

1. In your repo: **Settings** (top bar) → **Pages** (left sidebar)
2. Under "Build and deployment" → Source: **Deploy from a branch**
3. Branch: **main**, folder: **/ (root)** → **Save**
4. Wait 1-2 minutes, then visit `https://YOUR-USERNAME.github.io`

Your site is now live at the free address. The custom domain comes next.

---

## Step 5 — Add the custom domain in GitHub

Still in **Settings → Pages**:

1. Under "Custom domain", type exactly: `www.sajjadahamed.com`
2. Click **Save**

GitHub will say the DNS check is in progress or unsuccessful. That is expected —
you haven't added the DNS records yet. Do Step 6 now.

---

## Step 6 — Add DNS records at your registrar

Log in to your registrar (Cloudflare or Namecheap) → DNS settings for
sajjadahamed.com. Add FIVE records total.

### One CNAME record (this makes www work)

| Type  | Name / Host | Value / Target             |
|-------|-------------|----------------------------|
| CNAME | `www`       | `YOUR-USERNAME.github.io`  |

(Value ends with a dot at some registrars: `YOUR-USERNAME.github.io.` — either is fine.)

### Four A records (these make the bare domain redirect to www)

| Type | Name / Host | Value             |
|------|-------------|-------------------|
| A    | `@`         | `185.199.108.153` |
| A    | `@`         | `185.199.109.153` |
| A    | `@`         | `185.199.110.153` |
| A    | `@`         | `185.199.111.153` |

`@` means the bare domain. Some registrars want you to leave the field blank
instead, or type `sajjadahamed.com`.

**Cloudflare users:** set the proxy status to **DNS only** (grey cloud, not
orange) on all five records, or HTTPS will break.

**Delete any default records** your registrar pre-created for `@` or `www`
(parking pages, redirects) before saving.

Optional IPv6 — four AAAA records on `@`:
`2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153`

---

## Step 7 — Wait, then enable HTTPS

DNS usually propagates in 15-60 minutes (can take up to 24 hours).

1. Return to **Settings → Pages**
2. When the green checkmark appears next to your domain, tick **Enforce HTTPS**
3. If the tickbox is greyed out, wait longer and refresh — the certificate is
   still being issued

Done. `www.sajjadahamed.com` is live, and `sajjadahamed.com` redirects to it.

---

## Updating the site later

Edit any file directly on GitHub: open the file → pencil icon → edit →
**Commit changes**. Live in ~1 minute.

To add photos: open the `assets` folder → **Add file** → **Upload files**.

---

## If something breaks

| Symptom | Fix |
|---------|-----|
| "DNS check unsuccessful" | Wait longer; verify CNAME points to `USERNAME.github.io` with no typo |
| Site loads but no styling | The `assets` folder wasn't uploaded as a folder — re-upload it |
| 404 on homepage | File must be named exactly `index.html`, lowercase, in the root |
| HTTPS tickbox greyed out | Certificate still issuing; wait up to 24h |
| Bare domain doesn't redirect | The four A records are missing or wrong |

Check DNS propagation any time at dnschecker.org.
