# Path of Arrows — legal pages

Static pages published with GitHub Pages. They are the targets of the in-app
Settings links and of the App Store Connect **Privacy Policy URL** and
**Support URL** fields, so they must stay publicly reachable without a login.

Expected site: `https://daymonth.github.io/path-of-arrows-legal/`
(repository `DayMonth/path-of-arrows-legal` — create it before store submission).

Do not edit the three policy HTML files by hand: they are generated from the
Markdown sources in the game repository.

| Published page | Source |
| --- | --- |
| `privacy-policy.html` | `PRIVACY_POLICY.md` |
| `terms-of-service.html` | `TERMS_OF_SERVICE.md` |
| `technical-support.html` | `TECHNICAL_SUPPORT.md` |

Regenerate (from the game repository root), then publish:

```sh
python3 tools/build_legal_pages.py
```
