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

## Maintenance

- Update existing documentation instead of adding a duplicate guide.
- Remove stale instructions when scripts or project structure change.
- Do not create task summaries, scratch notes, or generated reports in the repository unless explicitly requested.
- Review Markdown links and code examples before committing documentation changes.
