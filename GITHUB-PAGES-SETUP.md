# Launching wrightcm.co on GitHub Pages (free) — step by step

No coding required. You'll do this once; after that, updates are two clicks.

Your site will host **100% free on GitHub**. GitHub automatically builds and
publishes it every time you push a change. (Netlify is just an alternative host —
you don't need it.)

---

## Part 1 — Get the project onto GitHub

The easiest tool for a non-coder is **GitHub Desktop** (free app). It turns
"pushing to GitHub" into clicking a button.

1. Download and install **GitHub Desktop**: https://desktop.github.com
2. Open it and **sign in** with your GitHub account.
3. Go to **File → Add Local Repository**.
4. Choose this folder:
   `C:\Users\jfw04\OneDrive\CM Firm\Marketing\WCM Website Builder\wrightcm-astro`
5. It will say "this directory is not a Git repository — create one?" → click
   **Create a repository** → then **Create Repository** on the next screen.
6. Click **Publish repository** (top right).
   - Name it `wrightcm` (or anything).
   - **Uncheck "Keep this code private"** (Pages on the free plan needs it public),
     OR leave private — GitHub Pages is now free for private repos too. Either works.
   - Click **Publish repository**.

Your code is now on GitHub. 🎉

---

## Part 2 — Turn on GitHub Pages

1. In your browser, go to your new repo on github.com
   (GitHub Desktop → **Repository → View on GitHub** opens it).
2. Click **Settings** (top menu) → **Pages** (left sidebar).
3. Under **Build and deployment → Source**, choose **GitHub Actions**.
   (You do NOT need to pick a branch — the workflow I already added handles it.)
4. That's it. Go to the **Actions** tab — you'll see a build running. When it
   finishes (green check, ~1–2 min), your site is live at a temporary address like
   `https://YOURUSERNAME.github.io/wrightcm`.

---

## Part 3 — Connect your domain wrightcm.co

### 3a. Tell GitHub about the domain
1. Repo → **Settings → Pages → Custom domain**.
2. Enter `wrightcm.co` and click **Save**.
   (I already included a `CNAME` file so this sticks.)

### 3b. Point the domain at GitHub (at your registrar)
Log in wherever you registered wrightcm.co (GoDaddy, Namecheap, Google Domains,
etc.) and open its **DNS settings**. Add these records:

**Four A records** (for the bare domain `wrightcm.co`):

| Type | Name/Host | Value |
|------|-----------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

**One CNAME record** (for `www`):

| Type | Name/Host | Value |
|------|-----------|-------|
| CNAME | www | YOURUSERNAME.github.io |

(Replace YOURUSERNAME with your GitHub username. Keep the trailing dot if your
registrar adds one.)

### 3c. Turn on HTTPS
Back in **Settings → Pages**, wait a few minutes, then check
**Enforce HTTPS**. (GitHub issues a free SSL certificate automatically. DNS can
take anywhere from a few minutes to a few hours to take effect.)

When DNS finishes propagating, **https://wrightcm.co is live.** ✅

---

## Part 4 — How to update the site later

Whenever you (or I) change a file in the `wrightcm-astro` folder:

1. Open **GitHub Desktop** — it lists what changed.
2. Type a short note in the "Summary" box (e.g. "Updated homepage headline").
3. Click **Commit to main**, then **Push origin** (top right).

GitHub rebuilds and republishes automatically in ~1–2 minutes. That's the whole
update loop.

---

## About editing here vs. pushing

- **I can edit the files** in your `wrightcm-astro` folder anytime (copy changes,
  new projects, etc.). Those edits save straight to your computer.
- **I can't push to your GitHub for you** — that needs your login, which stays
  private to you. So the flow is: *I make the change → you open GitHub Desktop →
  Commit → Push.* Two clicks.
- Most content lives in **`src/data/content.json`** (stats, projects, white papers,
  testimonials). You can edit that yourself in any text editor if you like, then
  Commit/Push.

---

## The contact form (do this after launch)

GitHub Pages can't process form submissions. To make the inquiry form email you:

1. Create a free account at https://formspree.io and make a form — it gives you a
   URL like `https://formspree.io/f/abcwxyz`.
2. Tell me the URL and I'll wire it into the contact page (a one-line change).

Until then the form shows a friendly "thanks" message and your **Calendly booking
widget already works**, so you can still capture meetings from day one.
