# Legal Page Template

Use the existing Draw Together legal pages as the starting point for each new app:

- Copy `draw-together-privacy.html` to `[app-id]-privacy.html`.
- Copy `draw-together-terms.html` to `[app-id]-terms.html`.
- Keep the shared structure: `.site-nav`, `.legal-body`, and `.site-footer`.

Replace these fields in both copied files:

- App name in the `<title>`, meta description, heading metadata, and legal text.
- Developer-facing dates, especially the `Last updated` date.
- App-specific descriptions, data types, Firebase/services, retention details, and any special notices.
- Contact details only if they differ from `nosami.dev.21@gmail.com`.

Then open `admin.html`, edit or add the app entry, and set:

- `privacyUrl` to `[app-id]-privacy.html`
- `termsUrl` to `[app-id]-terms.html`

Save in the admin panel, copy the generated JSON, and commit it as `apps.json`.
