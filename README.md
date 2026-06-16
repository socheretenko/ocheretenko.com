# ocheretenko.com

Personal portfolio of **Serhii Ocheretenko** — full-stack developer based in Kyiv.

A single, self-contained static page. No build step, no framework, no dependencies — just HTML, CSS, and a little vanilla JavaScript. Built for a fast load and a clean Lighthouse profile.

## Features

- Light / dark theme with system preference detection (no flash on load)
- Responsive editorial layout (Newsreader + Hanken Grotesk + JetBrains Mono)
- Full SEO setup: meta tags, Open Graph + Twitter cards, `Person` JSON-LD, sitemap, robots
- Complete favicon set (SVG, PNG 16–512, Apple touch, maskable) + web manifest
- Accessible, reduced-motion aware, keyboard-friendly

## Structure

```
.
├── index.html          # the entire site
├── favicon.ico         # root fallback icon
├── site.webmanifest    # PWA / install metadata
├── robots.txt          # crawler rules → sitemap
├── sitemap.xml         # single-URL sitemap
└── favicon/            # icons + social share image
    ├── favicon.svg
    ├── favicon-16.png
    ├── favicon-32.png
    ├── favicon-180.png
    ├── favicon-192.png
    ├── favicon-512.png
    ├── maskable-512.png
    └── og-image.png     # 1200×630 social preview
```

> All asset paths are root-absolute (`/favicon/…`, `/site.webmanifest`). Keep these files at the **repository / web root** so they resolve correctly.

## Local preview

It's a static site, so any static server works:

```bash
# Python
python3 -m http.server 8000

# or Node
npx serve .
```

Then open <http://localhost:8000>.

## Deployment — Cloudflare Pages

1. Push this repo to GitHub.
2. In Cloudflare → **Workers & Pages → Create → Pages → Connect to Git** and pick this repo.
3. Build settings:
   - **Framework preset:** None
   - **Build command:** *(empty)*
   - **Build output directory:** `/`
4. After the first deploy, add the custom domain **ocheretenko.com** under the project's **Custom domains**.

Every push to `main` redeploys automatically.

## License

© Serhii Ocheretenko. All rights reserved.
