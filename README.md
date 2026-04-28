# sweetest-public-pages

Public landing site for the [Sweetest](https://github.com/trevornogues/sweetest) mobile app.
Hosts the Privacy Policy and Terms of Service that the app links to from its
App Store / Google Play listings and from inside the app's settings screen.

Served by GitHub Pages from the `main` branch root.

## Live URLs

Once GitHub Pages is enabled (Settings → Pages → Source: `Deploy from a branch`,
Branch: `main`, Folder: `/`), the pages live at:

- Index: <https://trevornogues.github.io/sweetest-public-pages/>
- Privacy Policy: <https://trevornogues.github.io/sweetest-public-pages/privacy/>
- Terms of Service: <https://trevornogues.github.io/sweetest-public-pages/terms/>

These are the URLs to paste into App Store Connect and the Google Play Console.

## Structure

```
.
├── index.html              # Landing page with links to /privacy and /terms
├── privacy/
│   └── index.html          # Privacy Policy
├── terms/
│   └── index.html          # Terms of Service
├── assets/
│   └── style.css           # Shared styles
├── .nojekyll               # Tells GitHub Pages to serve files as-is (no Jekyll)
└── README.md
```

## Editing

Plain static HTML + CSS — no build step. Edit the files directly, commit, and
push to `main`; GitHub Pages will redeploy within a minute or two.

When updating the legal docs:

1. Bump the `Effective date` at the top of the affected page(s).
2. Commit with a message describing the change (e.g. `privacy: clarify retention period`).

## Custom domain (optional, future)

If you later point a custom domain at this site (e.g. `sweetest.app`):

1. Add a `CNAME` file at the root containing the domain.
2. Configure the DNS records as instructed in the GitHub Pages docs.
3. Update absolute paths in `index.html`, `privacy/index.html`, `terms/index.html`,
   and `assets/style.css` references — currently they're prefixed with
   `/sweetest-public-pages/` to work under the project-pages URL. With a custom
   apex domain you can switch them to `/`.
