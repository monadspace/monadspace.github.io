# Monad Space

Personal site for Monad Space, built with Astro and deployed to GitHub Pages.

## Stack

- **Astro 7** — static site, no framework components, no content collections
- **Tailwind CSS 4** — via `@tailwindcss/vite` plugin, theme configured in `src/styles/global.css`
- **Vite+** — unified toolchain (`vp` CLI) for install, lint, format, and tasks
- **pnpm** — package manager (via Vite+)

## Commands

| Command          | Purpose                      |
| ---------------- | ---------------------------- |
| `vp install`     | Install dependencies         |
| `vp run dev`     | Start dev server             |
| `vp run build`   | Build to `dist/`             |
| `vp run preview` | Preview production build     |
| `vp check`       | Format, lint, and type check |
| `vp check --fix` | Auto-fix format/lint issues  |

A pre-commit hook runs `vp check --fix` on staged files automatically.

## Project Structure

- `src/pages/` — routes (currently just `index.astro`, a minimal landing page)
- `src/layouts/Layout.astro` — HTML shell; head boilerplate, fonts, `<slot />`
- `src/styles/global.css` — Tailwind import and theme tokens (`@theme`)
- `public/` — static assets (currently empty; no favicon by design)

## Conventions

- Components are `.astro` files, lowercase-kebab naming
- TypeScript strict mode (`astro/tsconfigs/strict`)
- Keep the site static — no server endpoints or SSR
- Style with Tailwind utilities; design tokens go in `@theme` in `global.css`, not ad-hoc values
- Commit messages use Conventional Commits (`feat:`, `fix:`, `chore:`, `ci:`, …); keep commits atomic

## Deployment

Push to `main` triggers `.github/workflows/deploy.yaml`, which builds with the official Astro action and deploys to GitHub Pages. No manual deploy step.

## Documentation

Full Astro docs: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages or routes](https://docs.astro.build/en/guides/routing/)
- [Astro component syntax](https://docs.astro.build/en/basics/astro-components/)
- [Styling and Tailwind](https://docs.astro.build/en/guides/styling/)
- [Integrations (sitemap, partytown, etc.)](https://docs.astro.build/en/guides/integrations-guide/)

<!--VITE PLUS START-->

# Using Vite+, the Unified Toolchain for the Web

This project is using Vite+, a unified toolchain built on top of Vite, Rolldown, Vitest, tsdown, Oxlint, Oxfmt, and Vite Task. Vite+ wraps runtime management, package management, and frontend tooling in a single global CLI called `vp`. Vite+ is distinct from Vite, and it invokes Vite through `vp dev` and `vp build`. Run `vp help` to print a list of commands and `vp <command> --help` for information about a specific command.

Docs are local at `node_modules/vite-plus/docs` or online at https://viteplus.dev/guide/.

## Built-in Commands vs Scripts

`vp <name>` runs a built-in command. `vp run <name>` runs a `package.json` script or a `vite.config.ts` task. Scripts cannot overwrite built-ins, so `vp dev` and `vp run dev` may do different things. Check `package.json` and `vite.config.ts` first, and run `vp run <name>` when the project defines a script or task with that name.

## Review Checklist

- [ ] Run `vp install` after pulling remote changes and before getting started.
- [ ] Run `vp check` and `vp test` to format, lint, type check and test changes.
- [ ] Check if there are `vite.config.ts` tasks or `package.json` scripts necessary for validation, run via `vp run <script>`.
- [ ] If setup, runtime, or package-manager behavior looks wrong, run `vp env doctor` and include its output when asking for help.

<!--VITE PLUS END-->
