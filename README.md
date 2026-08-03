# Monad Space

A home for side projects, experiments, and ideas — with room to grow into community-driven efforts.

**👉 Visit [monadspace.com](https://monadspace.com)**

## Stack

- [Astro](https://astro.build) — static site
- [Tailwind CSS 4](https://tailwindcss.com) — via `@tailwindcss/vite`
- [Vite+](https://viteplus.dev) — unified toolchain (`vp` CLI)

## Commands

| Command          | Action                               |
| :--------------- | :----------------------------------- |
| `vp install`     | Install dependencies                 |
| `vp run dev`     | Start dev server at `localhost:4321` |
| `vp run build`   | Build production site to `dist/`     |
| `vp run preview` | Preview production build             |
| `vp check`       | Format, lint, and type check         |

## Deployment

Pushes to `main` deploy automatically to GitHub Pages via `.github/workflows/deploy.yaml`.
