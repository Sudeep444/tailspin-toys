---
description: 'Documentation standards for Tailspin Toys project documentation'
applyTo: '**/*.md'
---

# Documentation Instructions

Keep documentation accurate, concise, and aligned with the current Astro, SQLite, and npm-script architecture.

## Content

- Explain the user or contributor outcome first, then the steps needed to achieve it.
- Use the exact script names and paths from the repository. Do not invent a `scripts/` directory or a backend API that does not exist.
- Document changes to public behavior, setup, data workflows, testing, or repository structure in the nearest relevant document.
- Keep examples copyable and use fenced code blocks with the correct language.
- Prefer relative links for files in this repository and verify that referenced paths exist.
- Use inclusive, neutral language consistent with `CODE_OF_CONDUCT.md`.

## Project-specific details

- Mention Node.js 22.13 or later when documenting local setup.
- Explain that Astro pages are prerendered and query SQLite at build time.
- Describe schema changes together with their generated Drizzle migration.
- When documenting validation, distinguish unit tests, Playwright E2E tests, linting, and the two type-check commands.

## Commenting philosophy

- Comment the intent, trade-off, or decision behind the code rather than the mechanics of the code itself.
- Prefer comments that explain why a branch, workaround, or constraint exists, and why a particular API or data flow is shaped the way it is.
- Do not restate the code in prose. A comment that repeats the exact operation below it is noise and should be removed.
- Treat stale comments as bugs: update or remove them in the same change that modifies the related logic.
- Add brief comments only when the reasoning would be non-obvious to a future contributor, especially for edge cases, performance tuning, or compatibility workarounds.

## Code documentation expectations

- Every exported function in `db/` and `src/lib/` must have a TSDoc/JSDoc block that describes its purpose, parameters, and return value.
- Document injectable `db` arguments clearly so the testing pattern remains obvious and consistent.
- For reusable `.astro` components, document the public `Props` contract in TypeScript so the component API is self-explanatory.
- Keep types explicit in TypeScript: export function signatures with descriptive parameter and return types; avoid `any` unless it is absolutely unavoidable and documented.
- Prefer comments that explain decisions and constraints over implementation details. When a comment is no longer true, it must be edited or removed.

## TypeScript and formatting standards

- Prefer explicit TypeScript annotations on exported helpers, component props, and data contracts.
- Use interfaces or type aliases for public object shapes rather than repeating ad hoc object literals in multiple places.
- Keep code readable and consistent with the repository's ESLint setup; use the configured lint rules as the enforcement gate for mechanical issues such as unused names and other code-quality checks.
- For project-level conventions that are harder to lint automatically (such as comment intent), enforce them through code review and documentation so the standard stays clear for contributors.

## Maintenance

- Update existing documentation instead of adding a duplicate guide.
- Remove stale instructions when scripts or project structure change.
- Do not create task summaries, scratch notes, or generated reports in the repository unless explicitly requested.
- Review Markdown links and code examples before committing documentation changes.
