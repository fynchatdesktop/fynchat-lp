# FynChat landing page

The marketing site for [FynChat](https://github.com/fynchatdesktop) — a
Telegram-style messenger platform written in Go: a native desktop client built
with [Fyne](https://fyne.io), a Go + PostgreSQL backend, and FCP, its own
binary wire protocol.

Plain HTML, CSS and vanilla JavaScript. No build step, no dependencies.

## Local preview

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## Publishing (GitHub Pages via Actions)

The workflow in `.github/workflows/deploy.yml` builds nothing and deploys the
repo root straight to Pages on every push to `main`. One-time setup (must be
done in the web UI — the default `GITHUB_TOKEN` cannot enable Pages itself):

1. Repo **Settings → Pages → Build and deployment → Source**: pick
   **GitHub Actions**. If the first run already failed with
   *"Pages is not enabled"*, this is expected — enable it, then
   **Actions → re-run the failed job**.
2. Push to `main` (or re-run the workflow from the **Actions** tab).

The site appears at `https://fynchatdesktop.github.io/fynchat-lp/`.

## Structure

| Path | What it is |
| --- | --- |
| `index.html` | The whole page |
| `styles.css` | Telegram-inspired palette (`#3390EC` accent), dark + light themes |
| `script.js` | Theme toggle, mobile nav, lightbox, copy buttons, scroll reveal |
| `assets/` | Logo and screenshots, copied from `FynChat/fdesktop` |
| `.github/workflows/` | GitHub Pages deployment |

## License

MIT © 2026 FynChat — same as the rest of the platform.
