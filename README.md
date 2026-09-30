# sweetest-public-pages

Public landing site for the [Sweetest](https://github.com/trevornogues/sweetest) mobile app.
Hosts the Privacy Policy and Terms of Service that the app links to from its
App Store / Google Play listings and from inside the app's settings screen.

Served by GitHub Pages from the `main` branch root.

## Live URLs

Once GitHub Pages is enabled (Settings → Pages → Source: `Deploy from a branch`,
Branch: `main`, Folder: `/`), the pages live at:

- Index: <https://trevornogues.github.io/sweetest-public-pages/>
- Changelog: <https://trevornogues.github.io/sweetest-public-pages/changelog/>
- Privacy Policy: <https://trevornogues.github.io/sweetest-public-pages/privacy/>
- Terms of Service: <https://trevornogues.github.io/sweetest-public-pages/terms/>
- Account deletion: <https://trevornogues.github.io/sweetest-public-pages/delete-account/>
- Child Safety Standards: <https://trevornogues.github.io/sweetest-public-pages/child-safety/>

These are the URLs to paste into App Store Connect and the Google Play Console.

## Structure

```
.
├── index.html              # Landing page (storefront: features, screens, pricing, FAQ, founder)
├── changelog/
│   └── index.html          # Release notes, newest first
├── privacy/
│   └── index.html          # Privacy Policy
├── terms/
│   └── index.html          # Terms of Service
├── delete-account/
│   └── index.html          # Account deletion instructions
├── child-safety/
│   └── index.html          # CSAE/CSAM prevention standards
├── assets/
│   ├── style.css           # Shared styles (brand tokens at the top)
│   ├── app-icon.png, favicon.png, wordmark.png, og-image.jpg
│   └── screens/*.jpg       # 640x1056 app screenshots for the landing page
├── robots.txt, sitemap.xml, llms.txt
├── .nojekyll               # Tells GitHub Pages to serve files as-is (no Jekyll)
└── README.md
```

## Keeping the landing page honest

- After a release: add an entry to `changelog/index.html`, update `softwareVersion` and `dateModified` in the JSON-LD on `index.html`, and bump `lastmod` in `sitemap.xml`.
- After new reviews land: refresh the rating line in the hero and `ratingCount` in the JSON-LD.
- Only claim what the app does today and what the App Store listing says. No testimonials until real ones are collected (there is a commented-out block in `index.html` ready for them). Do not use em dashes in copy.

## Editing

Plain static HTML + CSS, no build step. Edit the files directly, commit, and
push to `main`; GitHub Pages will redeploy within a minute or two.

When updating the legal docs:

1. Bump the `Effective date` at the top of the affected page(s).
2. Commit with a message describing the change (e.g. `privacy: clarify retention period`).

## Custom domain (optional, future)

If you later point a custom domain at this site (e.g. `sweetest.app`):

1. Add a `CNAME` file at the root containing the domain.
2. Configure the DNS records as instructed in the GitHub Pages docs.
3. Update absolute paths in `index.html`, `privacy/index.html`, `terms/index.html`,
   and `assets/style.css` references, which currently they're prefixed with
   `/sweetest-public-pages/` to work under the project-pages URL. With a custom
   apex domain you can switch them to `/`.
