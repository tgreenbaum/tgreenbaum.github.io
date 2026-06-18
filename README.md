# Personal site

Single-page scroll portfolio. One file (`index.html`), no build step.

## Customize

Open `index.html` and swap these placeholders:

| Where | What |
|---|---|
| `<title>` and `meta description` | Page title and SEO description |
| `.nav__brand img` `src` | Your logo image (swap placeholder for `images/logo.svg` or similar) |
| `.hero__name` | Your name |
| `.hero__tagline` | Your one-liner |
| `.hero__bg` `background-image` URL | Hero background photo |
| `.hero__avatar` `background-image` URL | Your profile photo (square works best) |
| `#about` paragraphs | Your bio |
| `.work-card` blocks | Your projects (image, title, meta) |
| `mailto:hello@yourname.com` | Your email |
| `.contact__social` links | Your social URLs |

Tip: drop your own images into the `/images` folder and reference them with relative paths (e.g. `background-image: url('images/me.jpg')`).

**Hero image:** save your hero photo as `images/hero.jpg` (the HTML already points there). Profile photo can go at `images/avatar.jpg` — then update the `.hero__avatar` `background-image` URL in `index.html` to `url('images/avatar.jpg')`.

## Deploy to GitHub Pages

1. Create a repo on GitHub. If you want the site at `https://<username>.github.io`, name the repo exactly `<username>.github.io`. Otherwise any name works and the URL becomes `https://<username>.github.io/<repo>`.
2. Push these files:
   ```
   git init
   git add index.html README.md CNAME
   git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:<username>/<repo>.git
   git push -u origin main
   ```
3. In the repo on GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: `main`, folder: `/ (root)` → Save**.
4. Give it ~1 minute. Your site is live.

## Connect your custom domain

1. Edit `CNAME` and replace the placeholder with your bare domain (e.g. `yourname.com` — no `https://`, no trailing slash). Commit and push.
2. At your DNS provider, add records:
   - **Apex domain** (`yourname.com`): four A records pointing to GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **www subdomain**: one CNAME record pointing to `<username>.github.io`.
3. Back in **Settings → Pages**, enter your domain in the "Custom domain" field and tick **Enforce HTTPS** once the cert provisions (can take 15–60 min).

## Local preview

Just double-click `index.html` — it runs in any browser, no server needed. For a closer-to-production preview:

```
python3 -m http.server 8000
# then open http://localhost:8000
```
