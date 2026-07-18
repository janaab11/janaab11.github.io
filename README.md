# manas

Personal blog. Built with [Astro](https://astro.build) (based on the [Cactus](https://github.com/chrismwilliams/astro-theme-cactus) theme).

## Run locally

Requires **Node ≥ 22.12**.

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # static output → dist/
```

## Add a post

Long-form goes in `content/posts/`, short-form in `content/notes/`. Markdown (`.md`) or MDX (`.mdx`).

**Post** — `content/posts/my-post.md`:

```md
---
title: "My post"
description: "One-line summary, shown in the listing and RSS."
publishDate: "2026-07-18"
tags: ["ml"]        # optional
draft: false         # optional; true hides it
---

Body text. Use a `.mdx` file to import and render components inline.
```

### Math

Use an `.mdx` post and the `<Math>` component (LaTeX as a string prop, rendered at build time):

```mdx
import Math from "@/components/Math.astro";

Inline <Math tex="\nabla f" /> and display:

<Math tex="\frac{e^{z_i}}{\sum_j e^{z_j}}" display />
```

**Note** — `content/notes/my-note.md`:

```md
---
title: "A short note"
publishDate: "2026-07-18T00:00:00Z"   # notes need a full ISO timestamp
---

Short thought.
```

## Deploy

Push to `main` — GitHub Actions builds and publishes to GitHub Pages ([.github/workflows/deploy.yml](.github/workflows/deploy.yml)). No manual build or upload.
