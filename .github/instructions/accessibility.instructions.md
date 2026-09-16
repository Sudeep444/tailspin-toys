---
description: 'Accessibility requirements for Tailspin Toys UI changes'
applyTo: '**/*.{astro,css}'
---

# Accessibility Instructions

Treat accessibility as part of the feature, not a follow-up task. The site is a static Astro application, so prefer semantic HTML and native browser behavior over custom JavaScript.

## Semantics and names

- Use the element that matches the interaction: links for navigation, buttons for actions, headings for hierarchy, and lists for collections.
- Give every interactive control an accessible name. Visible text is preferred; use `aria-label` only when no visible label is appropriate.
- Keep heading levels ordered and use one clear page heading where practical.
- Do not add `role="menu"` or `role="menuitem"` to ordinary navigation. Use those roles only for a complete application-style menu with the required keyboard behavior.
- Mark decorative icons and SVGs with `aria-hidden="true"`. Provide an accessible name when an icon conveys meaning.

## Keyboard and focus

- All interactive elements must be reachable and usable with the keyboard.
- Preserve the browser's native focus behavior and add a visible focus style such as `focus:ring-2 focus:ring-blue-500 focus:outline-none`.
- Dismissible menus and dialogs must support Escape and should return focus to the control that opened them.
- Do not use pointer-only hover behavior to expose essential content or actions.

## Visual presentation

- Maintain sufficient contrast in the dark slate color palette.
- Do not communicate status by color alone; include text or an accessible label.
- Keep text readable at responsive widths and avoid fixed layouts that require horizontal scrolling.
- Loading or asynchronous status messages should use `role="status"` and `aria-live="polite"` when appropriate.

## Verification

- Add or update Playwright coverage for meaningful interactive or accessibility behavior.
- Run the E2E and accessibility checks through the `quality-checks` skill.
- Every interactive element added to the UI must include a descriptive `data-testid` for testability.
