# markburke.io

Personal blog built with Astro, deployed on Cloudflare Pages.

## Writing a new blog post

1. Create a new `.md` file in `src/content/blog/`:

```bash
touch src/content/blog/my-new-post.md
```

2. Add frontmatter at the top:

```markdown
---
title: 'My Post Title'
description: 'A short description for SEO and previews.'
pubDate: 'Apr 02 2026'
---

Your content here. Standard markdown.
```

3. Preview locally:

```bash
npm run dev
```

4. Publish — commit and push:

```bash
git add .
git commit -m "new post: my post title"
git push
```

Cloudflare Pages auto-deploys from the `main` branch.

## Frontmatter fields

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | Post title |
| `description` | Yes | Short description for SEO/previews |
| `pubDate` | Yes | Publication date (e.g. `'Apr 02 2026'`) |
| `updatedDate` | No | Last updated date |
| `heroImage` | No | Path to hero image in `src/assets/` |

## Commands

| Command | Action |
|---------|--------|
| `npm run dev` | Start dev server at `localhost:4321` |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build locally |

## Stack

- [Astro](https://astro.build) — static site generator
- [Tailwind CSS](https://tailwindcss.com) — utility-first CSS
- [Cloudflare Pages](https://pages.cloudflare.com) — hosting + CDN
