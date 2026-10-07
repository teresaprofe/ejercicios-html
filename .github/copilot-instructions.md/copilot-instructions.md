# Copilot instructions for this repo

This workspace is a small static HTML/CSS teaching project. There is no build toolchain, package manager, or test suite. The expected workflow is to edit the HTML files directly and open them in a browser to validate the result.

## Project structure
- `Introducción a HTML y CSS.html`: main interactive lesson page. It is a single-file app with embedded CSS and JavaScript.
- `Empresas del sector informático.html`: static catalog page for three IT companies; it uses a clean card layout and external links.
- `ejemplo.html`: empty starter file intended for quick experiments or duplicated templates.

## Architecture and conventions
- Keep each page self-contained: CSS is embedded in a `<style>` block and JavaScript is embedded in a `<script>` block when present.
- Prefer semantic HTML (`<article>`, `<section>`, `<nav>`, `<header>`, `<footer>`) over generic wrappers.
- The interactive lesson page uses a data-driven pattern: the `L` array in `Introducción a HTML y CSS.html` defines each lesson with `t`, `e`, `r`, and `c` fields, and `show(i)` renders the current lesson into the page.
- When adding a new lesson, follow the same object structure as the existing entries and update the navigation automatically through `L.forEach(...)`.
- Styling is custom CSS variables (`--bg`, `--card`, `--accent`, etc.) and should stay consistent with the existing palette and dark-mode pattern.

## Editing guidance
- Preserve the Spanish educational tone used throughout the files; content is written for students and classroom tasks.
- Keep examples concise and accessible; these pages are meant to teach concepts rather than build production-scale UI.
- When adding links, prefer plain `target="_blank" rel="noopener noreferrer"` patterns like the ones in `Empresas del sector informático.html`.
- Reuse existing class names and layout patterns before inventing new ones; the project uses lightweight, hand-written CSS rather than component frameworks.

## Validation workflow
- No automated checks exist. Validate changes by opening the relevant HTML file in a browser.
- For the lesson page, verify the lesson navigation still works and that the editable code preview still renders correctly.
- For the company page, confirm the cards, links, and responsive grid remain visually aligned.

## Do not assume
- Do not add Node, npm, Vite, React, or a build system unless the user explicitly asks for a larger project.
- Do not split the styling into external files or frameworks; this repo is intentionally minimal and static.
- Do not replace the embedded lesson data model with a different architecture unless the task specifically requires it.

## Good examples in this codebase
- Dynamic lesson rendering: `Introducción a HTML y CSS.html` (`const L = [...]`, `show(i)`, `nav` generation)
- Card-based static layout: `Empresas del sector informático.html` (`.grid`, `.card`, `article.card`)
- Minimal starter template: `ejemplo.html` for a blank HTML canvas

If you need a convention clarified for a specific edit, ask for the target page and I can align the change to the existing style and structure.
