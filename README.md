# Reform AI — Marketing Website

Static site with the landing page, Privacy Policy, Terms of Service, and Support page for the Reform AI iOS app.

## How to deploy on GitHub Pages (step by step)

### 1. Create a public repo on GitHub

1. Go to https://github.com/new
2. Repository name: **`airemodel`** (or whatever you want — the name ends up in the URL)
3. Description: optional, e.g. "Reform AI — Marketing site"
4. Visibility: **Public**
5. Do NOT initialize with README, .gitignore, or license — leave it empty.
6. Click **Create repository**.

### 2. Push these files to the new repo

Open Terminal and run (replace `<YOUR_GH_USER>` with your GitHub username):

```bash
cd /Users/marc/Documents/ia-remodeling/marketing/website
git init -b main
git add .
git commit -m "Initial public marketing site"
git remote add origin https://github.com/<YOUR_GH_USER>/airemodel.git
git push -u origin main
```

If git asks for authentication, use a Personal Access Token (https://github.com/settings/tokens) instead of your password.

### 3. Enable GitHub Pages

1. Go to your repo on GitHub.
2. Click **Settings** (tab at top).
3. In the left sidebar, click **Pages**.
4. Under **Source**, pick:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **Save**.
6. Wait ~30 seconds. The page reloads showing your URL:
   `https://<YOUR_GH_USER>.github.io/airemodel/`

### 4. Your URLs

Once published, these are the URLs you paste in App Store Connect:

| Field | URL |
|---|---|
| Privacy Policy | `https://<YOUR_GH_USER>.github.io/airemodel/privacy.html` |
| Terms of Service | `https://<YOUR_GH_USER>.github.io/airemodel/terms.html` |
| Support URL | `https://<YOUR_GH_USER>.github.io/airemodel/support.html` |
| Marketing URL | `https://<YOUR_GH_USER>.github.io/airemodel/` |

### 5. Verify

Open each URL in a browser. They should load with proper styling. If the CSS doesn't load, give GitHub 1-2 minutes to finish deploying.

## Customize before publishing

Edit each `.html` file and replace:

- `privacy@airemodelapp.com` → your real privacy contact email
- `support@airemodelapp.com` → your real support email
- `Marc Montane Marti` → if you want a different legal name / company
- `Barcelona, Spain` in `terms.html` → your real city if different
- "Download on the App Store" CTA on `index.html` → real App Store URL once your app is live

## Updating the site later

After any change:

```bash
cd /Users/marc/Documents/ia-remodeling/marketing/website
git add .
git commit -m "Update privacy policy"
git push
```

GitHub Pages re-deploys automatically in ~30 seconds.

## Later: connect a custom domain

When you buy `airemodelapp.com`:

1. Add a file named `CNAME` to this folder containing `airemodelapp.com`.
2. In Namecheap (or wherever the domain is): add a CNAME record pointing `www` to `<YOUR_GH_USER>.github.io`, and ALIAS / ANAME for the apex to GitHub Pages IPs (see GitHub docs).
3. In GitHub repo Settings → Pages, paste `airemodelapp.com` as the custom domain.
4. Enable "Enforce HTTPS" once the certificate is issued (~10 min).

Then your URLs become `https://airemodelapp.com/privacy.html` etc.
