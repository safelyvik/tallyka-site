# tallyka-site

Public static marketing/legal site for **Tallyka**, served via GitHub Pages at
<https://safelyvik.github.io/tallyka-site/>.

**Do not edit anything here.** This repo is a mirror. The source of truth is
`docs/` in the private `safelyvik/Tallyka` repo — run `scripts/publish-site.sh`
there to update, which rsyncs `docs/` over this repo and pushes.

Everything except `README.md`, `.nojekyll` and `CNAME` is overwritten on each
publish, so local edits will be silently discarded.

## What's here

| File | Purpose |
|---|---|
| `index.html` | Landing page |
| `privacy.html` | Privacy policy — **required by both app stores**, linked from the app's Settings screen |
| `terms.html` | Terms of service — also linked from Settings |
| `route.html` | Standalone trip-route viewer. Exported PDF reports link here with the route encoded in the URL **fragment**, which browsers never send to a server — so route data reaches no backend, and this page needs none. |
| `legal.css`, `icon.png`, `badge-*.svg` | Shared assets |

## Why this repo is public

GitHub Pages needs it, and it has to be public regardless: the privacy policy
and terms must be reachable by app-store reviewers and by people who have not
installed anything. Nothing sensitive belongs here — no code, no keys, no
config. If you want to add any of those, they go in the private repo.

## Custom domain

When `tallyka.com.au` is bought: add a `CNAME` file here, point the DNS record
at GitHub Pages, then update `VITE_ROUTE_VIEWER_URL` and the two Settings links
in the private repo. Do this **before first release** — route links already
written into exported PDFs keep working only as long as the host they were
generated with does.
