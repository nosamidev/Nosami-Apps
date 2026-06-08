# Nosami Apps — Add New App Prompt
# ─────────────────────────────────────────────────────────────────────────────
# HOW TO USE:
#   1. Fill in the APP INFORMATION section below
#   2. Open VS Code with this repo
#   3. Open GitHub Copilot Chat (or Claude in VS Code)
#   4. Paste the entire prompt below (starting from the line "You are helping...")
# ─────────────────────────────────────────────────────────────────────────────

# ════════════════════════════════════════
#   APP INFORMATION  ← Fill this in
# ════════════════════════════════════════

APP_SLUG=my-app-name           # lowercase-with-dashes, used for folder name
APP_NAME=My App Name           # Display name shown on the site
APP_TAGLINE=Short one-liner about what the app does
APP_DESCRIPTION=A 2–3 sentence description of what the app does and who it's for.
APP_ICON_EMOJI=📱              # Emoji icon (or replace with real icon later)
APP_CATEGORY=Productivity      # e.g. Business, Utility, Productivity, Lifestyle
APP_PLAY_URL=https://play.google.com/store/apps/details?id=YOUR.PACKAGE.NAME
APP_STATUS=live                # "live" or "coming-soon"

# Features (one per line, starts with -)
APP_FEATURES=
- Feature one
- Feature two
- Feature three
- Feature four

# Android permissions used by this app
APP_PERMISSIONS=
- INTERNET — used for [explain why]
- CAMERA — used for [explain why]

# Does this app collect ANY data? (yes/no)
APP_COLLECTS_DATA=no

# If yes, describe what data is collected:
APP_DATA_COLLECTED=N/A

# Third-party SDKs used (Firebase, Admob, etc.) — leave empty if none
APP_THIRD_PARTY_SDKS=None

# ════════════════════════════════════════
#   PROMPT (paste from here into AI chat)
# ════════════════════════════════════════

---
You are helping maintain the Nosami Apps website — a GitHub Pages site for an Android app developer.

The project structure is:
```
nosami-site/
├── index.html            ← homepage (app grid)
├── style.css             ← shared styles
├── privacy.html          ← global privacy policy
├── terms.html            ← terms of service
└── apps/
    └── [app-slug]/
        ├── index.html    ← app detail page
        └── privacy.html  ← per-app privacy policy
```

## Task: Add a new app

Using the information below, do the following:

### 1. Create `apps/[APP_SLUG]/index.html`
Copy the structure of `apps/sample-app/index.html` and fill in:
- Page title: "[APP_NAME] — Nosami Apps"
- Meta description: [APP_TAGLINE]
- App icon: [APP_ICON_EMOJI]
- App name: [APP_NAME]
- Tagline: [APP_TAGLINE]
- Google Play link: [APP_PLAY_URL]
- About paragraph: [APP_DESCRIPTION]
- Features list: [APP_FEATURES]
- Permissions section: [APP_PERMISSIONS]
- Privacy summary: based on APP_COLLECTS_DATA

### 2. Create `apps/[APP_SLUG]/privacy.html`
Copy the structure of `apps/sample-app/privacy.html` and fill in:
- App name: [APP_NAME]
- Section 1 (Data We Collect): if APP_COLLECTS_DATA=no, use the "fully offline / no data" version. If yes, describe APP_DATA_COLLECTED.
- Section 2 (Third-Party Services): list APP_THIRD_PARTY_SDKS. If none, say so.
- Section 3 (Permissions): list APP_PERMISSIONS and explain each.
- Keep all other sections unchanged.

### 3. Update `index.html`
Add a new `.app-card` entry inside the `.app-grid` div for this app:
- Icon: [APP_ICON_EMOJI]
- Name: [APP_NAME]
- Category: [APP_CATEGORY]
- Description: [APP_TAGLINE]
- Badge: "● Live on Play" (badge-green) if APP_STATUS=live, or "In progress" (badge-blue) if coming-soon
- Link: `apps/[APP_SLUG]/index.html`

### Rules
- Never modify `style.css`, `privacy.html` (global), or `terms.html`
- Keep all `<!-- ✏️ UPDATE -->` comments in new files so future edits are easy
- All paths in the new app folder must use `../../` to reference root files
- Do not invent features, permissions, or data practices — only use what is specified above

## App Information

APP_SLUG: [APP_SLUG]
APP_NAME: [APP_NAME]
APP_TAGLINE: [APP_TAGLINE]
APP_DESCRIPTION: [APP_DESCRIPTION]
APP_ICON_EMOJI: [APP_ICON_EMOJI]
APP_CATEGORY: [APP_CATEGORY]
APP_PLAY_URL: [APP_PLAY_URL]
APP_STATUS: [APP_STATUS]
APP_FEATURES: [APP_FEATURES]
APP_PERMISSIONS: [APP_PERMISSIONS]
APP_COLLECTS_DATA: [APP_COLLECTS_DATA]
APP_DATA_COLLECTED: [APP_DATA_COLLECTED]
APP_THIRD_PARTY_SDKS: [APP_THIRD_PARTY_SDKS]
