# AGENTS.md

## Repository structure

Two projects in one repo:

- **Root level** — Vanilla HTML/CSS static pages (`index.html`, `portafolio.html`, etc.). No build step.
- **`mi-app/`** — React 19 + Vite 8 SPA (the main project). ES modules (`"type": "module"`).

## Commands (run from `mi-app/`)

```sh
npm run dev      # dev server (Vite)
npm run build    # production build → dist/
npm run preview  # preview production build
npm run lint     # ESLint flat config (JSX only, no TS)
```

No test, typecheck, or formatter commands exist.

## Notable

- **No TypeScript** — project uses `.jsx` files. The `@types/react` packages in `devDependencies` are unused.
- **No formatter config** — no Prettier, Biome, or `.editorconfig`.
- **No CI, no pre-commit hooks, no test framework.**
- **EmailJS credentials** for the contact form are hardcoded in `mi-app/src/App.jsx:103-105` (service ID, template ID, public key).
- **`estilos.css` is missing** — referenced by `index.html` and `pagina1/2.html` but does not exist on disk.
- **Duplicated DOCTYPE** — `pagina1.html`, `pagina2.html`, `pagina3.html` have two `<html>` tags (invalid HTML).
- **`mi-app/` is untracked** — not yet committed to git.
- **`CV_Personal.pdf` was deleted** from disk but still referenced in `mi-app/src/App.jsx:192` and tracked by git.
- **`book copy/`** is an SB Admin 2 Bootstrap template (not part of the main app).
