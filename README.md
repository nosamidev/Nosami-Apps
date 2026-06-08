# nosami-site

> Official website for Nosami Apps — app showcase, privacy policies, and terms of service.
> Hosted on GitHub Pages. No build tools. Pure HTML/CSS.

## Live URLs (after deployment)

| Page | URL |
|------|-----|
| Homepage | `https://nosamiapps.github.io/nosami-site/` |
| Privacy Policy | `https://nosamiapps.github.io/nosami-site/privacy.html` |
| Terms of Service | `https://nosamiapps.github.io/nosami-site/terms.html` |
| App page example | `https://nosamiapps.github.io/nosami-site/apps/sample-app/` |
| App privacy example | `https://nosamiapps.github.io/nosami-site/apps/sample-app/privacy.html` |

---

## Project Structure

```
nosami-site/
├── index.html                   ← Homepage (app grid showcase)
├── style.css                    ← Shared styles for all pages
├── privacy.html                 ← Global privacy policy (all apps)
├── terms.html                   ← Terms of service (all apps)
├── ADD_NEW_APP.prompt.md        ← VS Code prompt to add a new app
└── apps/
    └── [app-slug]/
        ├── index.html           ← App detail page
        └── privacy.html        ← Per-app privacy policy
```

---

## Setup: Deploy to GitHub Pages

### Step 1 — Create the repository
1. Go to [github.com/new](https://github.com/new)
2. Repository name: `nosami-site`
3. Visibility: **Public**
4. Do NOT initialize with README
5. Click **Create repository**

### Step 2 — Push the files
```bash
git init
git add .
git commit -m "initial: nosami apps website"
git branch -M main
git remote add origin https://github.com/nosamiapps/nosami-site.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages
1. Go to your repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / Folder: `/ (root)`
4. Click **Save** — live in ~2 minutes

---

## Google Play — What URLs to Submit

When publishing an app on the **Google Play Console**, use these URLs:

| Field | URL |
|-------|-----|
| Privacy Policy (app-specific) | `https://nosamiapps.github.io/nosami-site/apps/[app-slug]/privacy.html` |
| Privacy Policy (global fallback) | `https://nosamiapps.github.io/nosami-site/privacy.html` |
| Developer website | `https://nosamiapps.github.io/nosami-site/` |
| Email | `contact@nosamiapps.com` |

**Important:** Google Play requires a Privacy Policy URL for every app. Use the per-app URL for best practice.

---

## Adding a New App (VS Code workflow)

1. Open `ADD_NEW_APP.prompt.md` in VS Code
2. Fill in the `APP INFORMATION` section at the top (slug, name, features, etc.)
3. Open **GitHub Copilot Chat** or **Claude for VS Code**
4. Paste the prompt section (from "You are helping..." to the end of the file)
5. The AI will generate:
   - `apps/[your-app]/index.html`
   - `apps/[your-app]/privacy.html`
   - Updated card in `index.html`
6. Review, then commit and push

---

## Manual Checklist for Each New App

Before going live on Google Play, verify:

- [ ] `apps/[slug]/index.html` created with correct app name, description, Play Store link
- [ ] `apps/[slug]/privacy.html` created with accurate data practices and permissions
- [ ] App card added to `index.html` (homepage grid)
- [ ] `contact@nosamiapps.com` is your real, monitored email
- [ ] Privacy Policy URL tested and accessible
- [ ] "Last updated" date is current
- [ ] Pushed to GitHub and GitHub Pages is live

---

## Customization Notes

- **Email**: Replace `contact@nosamiapps.com` in `privacy.html`, `terms.html`, and each app privacy page
- **Screenshots**: In each app's `index.html`, replace `<div class="screenshot-placeholder">` with real `<img src="screenshots/1.png" alt="...">` tags
- **App icon**: Replace the emoji in `.app-detail-icon` with a real `<img>` tag once you have an icon file
- **Dates**: Update "Last updated" dates in legal pages when you make changes
