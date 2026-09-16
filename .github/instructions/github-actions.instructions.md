---
description: 'GitHub Actions workflow authoring and maintenance'
applyTo: '.github/workflows/**/*.{yml,yaml}'
---

# GitHub Actions Instructions

Workflows must be secure, deterministic, and explicit about the permissions they require.

## Workflow design

- Set a top-level `permissions` block and use the smallest permissions needed.
- Keep jobs focused and give steps descriptive names.
- Pin actions to a major version already used in the repository unless there is a specific reason to update them.
- Use the repository's supported Node.js version from `package.json`.
- Prefer existing npm scripts over duplicating build, lint, type-check, database, or test commands in shell steps.
- Keep pull-request workflows safe for forked contributions; never expose secrets to untrusted code.

## Repository-specific checks

- Install dependencies with the lockfile (`npm ci`).
- Use the `quality-checks` skill guidance when changing or validating test and lint behavior.
- Run the static build before browser tests when a workflow needs a built site.
- Database setup must happen through the existing npm scripts so migrations and seed data stay consistent.

## Review checklist

- Verify triggers are limited to the branches and paths that need the workflow.
- Confirm permissions are explicit and no token or secret is printed.
- Avoid broad write permissions, arbitrary shell input, and unpinned third-party downloads.
- Document non-obvious workflow steps with short comments.
