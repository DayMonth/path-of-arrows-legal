# Path of Arrows — legal pages

Live site: **https://daymonth.github.io/path-of-arrows-legal/**
Repository: `DayMonth/path-of-arrows-legal` (public, GitHub Pages from `main` / root).

These pages are the targets of the in-app Settings links (`LEGAL_BASE` in
`src/app/app.gd`) and of the App Store Connect **Privacy Policy URL** and
**Support URL** fields, so they must stay publicly reachable without a login.

| Published page | URL | Source |
| --- | --- | --- |
| `index.html` | `/` | hand-written landing page |
| `privacy-policy.html` | `/privacy-policy.html` | `PRIVACY_POLICY.md` |
| `terms-of-service.html` | `/terms-of-service.html` | `TERMS_OF_SERVICE.md` |
| `technical-support.html` | `/technical-support.html` | `TECHNICAL_SUPPORT.md` |

Do not edit the three policy HTML files by hand: they are generated from the
Markdown sources in the game repository.

## Publishing an update

1. Edit the Markdown source in the game repository root.
2. Regenerate and verify:

   ```sh
   python3 tools/build_legal_pages.py
   python3 tools/build_legal_pages.py --check
   ```

3. Copy the regenerated pages into the published repository and push:

   ```sh
   SRC="$(pwd)/legal"
   git clone git@github.com:DayMonth/path-of-arrows-legal.git /tmp/poa-legal
   cp "$SRC"/*.html "$SRC"/.nojekyll /tmp/poa-legal/
   cd /tmp/poa-legal
   git add -A && git commit -m "Update legal pages" && git push
   ```

GitHub Pages rebuilds automatically; check `gh api
repos/DayMonth/path-of-arrows-legal/pages --jq .status` until it reports
`built`, then reload the page.

Keep the filenames stable — the app and the store listings hard-code them.
