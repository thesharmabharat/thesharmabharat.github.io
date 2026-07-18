# The Undercurrent Show

A blog built with [Astro](https://astro.build), hosted for free on Cloudflare Pages.
Domain: **theundercurrentshow.com** (registered at Namecheap).

## Run it locally

```bash
cd undercurrent-show
npm install       # first time only
npm run dev       # open http://localhost:4321
```

`npm run build` outputs the static site to `dist/`. `npm run preview` serves that build.

## Writing a post

Every `.md` file in `src/content/blog/` becomes a post automatically.
Copy `welcome.md`, rename it, and edit the frontmatter at the top:

```markdown
---
title: 'Your post title'
description: 'One-line summary shown in previews and search results.'
pubDate: 'Jul 20 2026'
heroImage: '../../assets/blog-placeholder-2.jpg'
---

Write your article in Markdown here.
```

Drop images into `src/assets/` and point `heroImage` at them. The filename
(minus `.md`) becomes the URL: `welcome.md` → `/blog/welcome/`.

## What to edit for branding

| File | Controls |
|------|----------|
| `src/consts.ts` | Site title + description |
| `src/pages/index.astro` | Homepage / hero |
| `src/pages/about.astro` | About page |
| `src/components/Header.astro` | Nav + social links |
| `src/components/Footer.astro` | Footer + social links |
| `src/styles/global.css` | Colors, fonts, spacing |
| `astro.config.mjs` | `site:` URL (already set) |

## Deploy to Cloudflare Pages

1. Push this folder to a GitHub repo.
2. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → connect the repo.
3. Build settings:
   - **Framework preset:** Astro
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
4. Deploy. Then add the custom domain `theundercurrentshow.com` under the
   project's **Custom domains** tab and follow the DNS instructions.
