# Deploying to www.wrightcm.co

The site is a static build — it can deploy to any static host. Recommended: **Netlify** (free tier, built-in form handling, easy custom domain).

## Option A — Netlify (recommended)

### 1. Put the project on GitHub (one time)
- Create a free GitHub account if needed.
- Create a new repository and upload this `wrightcm-astro` folder (or use GitHub Desktop / `git`).

### 2. Connect Netlify
1. Sign up at https://netlify.com (free).
2. **Add new site → Import an existing project → GitHub** → pick the repo.
3. Build settings (Netlify auto-detects Astro):
   - **Build command:** `npm run build`
   - **Publish directory:** `dist`
4. Click **Deploy**. You'll get a temporary URL like `random-name.netlify.app`.

### 3. Connect the domain wrightcm.co
1. In Netlify: **Domain settings → Add a domain →** enter `wrightcm.co`.
2. Netlify shows DNS records. At your domain registrar (where you bought wrightcm.co), either:
   - Point the domain's nameservers to Netlify (easiest), **or**
   - Add the `A` / `CNAME` records Netlify provides.
3. Netlify issues a free HTTPS certificate automatically. Live in minutes–hours (DNS propagation).

### 4. Turn on the contact form (optional but recommended)
The form is currently a demo. To make it deliver to your inbox via **Netlify Forms**:
1. In `src/pages/contact.astro`, on the `<form>` tag add: `name="inquiry"` and `data-netlify="true"`.
2. Add a hidden input inside the form: `<input type="hidden" name="form-name" value="inquiry" />`.
3. Remove the `onsubmit=...` demo handler.
4. Redeploy. Submissions appear in Netlify → **Forms**, and you can set email notifications to jwright@wrightcm.co.

## Option B — Cloudflare Pages
Same idea: connect the GitHub repo, build command `npm run build`, output `dist`, then add `wrightcm.co` under **Custom domains**. (Use Formspree or HubSpot for the form here.)

## Updating the site after launch
1. Edit `src/data/content.json` (or a page in `src/pages/`).
2. Commit/push to GitHub → the host rebuilds and redeploys automatically.
(Or run `npm run build` and drag the `dist/` folder onto Netlify for a manual deploy.)

## Notes
- The Calendly booking widget is already wired on the Contact page (`calendly.com/jwright-wrightcm/30min`).
- Testimonials are off until you set `testimonials.enabled: true` in content.json.
- Update the production URL in `astro.config.mjs` if the final domain differs.
