# Workspace Instructions

## Project Overview

A frontend learning project exploring **Vite**, **Tailwind CSS v4**, and **DaisyUI v5** integration. Plain HTML — no JS framework.

## Tech Stack

| Tool              | Version | Notes                                      |
| ----------------- | ------- | ------------------------------------------ |
| Vite              | ^7.x    | Build tool & dev server                    |
| Tailwind CSS      | ^4.x    | CSS-first config (no `tailwind.config.js`) |
| @tailwindcss/vite | ^4.x    | Vite plugin for Tailwind                   |
| DaisyUI           | ^5.x    | Component library loaded as a CSS plugin   |

## Commands

```bash
npm run dev      # Start dev server (hot reload)
npm run build    # Production build → dist/
npm run preview  # Preview production build locally
```

## Conventions

### CSS Setup (Tailwind v4 CSS-first)

Tailwind and DaisyUI are configured entirely in `src/style.css` — **no `tailwind.config.js`**:

```css
@import "tailwindcss";
@plugin "daisyui";
```

Add custom themes, plugins, or `@theme` overrides in this file.

### Styling Patterns

- Use **Tailwind utility classes** for layout, spacing, and typography directly in HTML.
- Use **DaisyUI component classes** (e.g., `btn`, `card`, `modal`, `badge`) for pre-styled components.
- Combine both freely: `class="btn btn-primary text-lg"`.

### HTML Structure

- Single-page app rooted in `index.html` at the project root.
- CSS is linked via `<link rel="stylesheet" href="./src/style.css">`.
- No bundled JS entry point by default — add a `<script type="module">` or `src/main.js` if logic is needed.

## Key Files

| File             | Purpose                                      |
| ---------------- | -------------------------------------------- |
| `index.html`     | Main page — markup lives here                |
| `src/style.css`  | Tailwind + DaisyUI imports and custom styles |
| `vite.config.js` | Vite config with Tailwind plugin             |
| `package.json`   | Dependencies and npm scripts                 |

## Pitfalls

- **Don't create `tailwind.config.js`** — Tailwind v4 uses CSS-first configuration.
- DaisyUI v5 component class names may differ from v4 docs; prefer the [v5 docs](https://daisyui.com/components/).
- `public/` folder is served as static assets at `/`.
