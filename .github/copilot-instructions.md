## Quick orientation for AI coding assistants

This is a small, static marketing site (no build step). Be concise: edits should be safe, minimal, and aligned to the existing file structure.

Key facts (big picture)
- Files are plain HTML in the repo root: `index.html`, `blog.html`, `privacy.html`, `terms.html` plus blog posts in `blog/`.
- Styling uses Tailwind CSS (via CDN) and Font Awesome (via CDN). There's no npm/webpack/postcss configuration—no build pipeline.
- JavaScript is minimal/vanilla for UI interactions (mobile menu, FAQ accordion). No server-side code or APIs in this repository.

Developer workflows (what to do and how)
- Edit content directly in the HTML files with a text editor (VS Code recommended). After edits, test locally by opening the file in a browser (`Open with → Chrome/Safari`).
- Deployment: follow `QUICK_START.md` — files are uploaded to a hosting control panel (wpfixit) into the web root. Keep filenames and paths unchanged to preserve URLs (e.g., `blog/mastering-...html`).
- No automated tests or CI in this repo. Do not add build-tooling unless the team asks for it; prefer minimal, low-risk changes.

Project-specific conventions and patterns
- Keep the root filenames unchanged. Public URLs are expected to be exact (see `QUICK_START.md` test URLs).
- CTA / contact links point to an external contact page (`https://websitemarketinghq.com/contact`). When updating CTAs, update all instances (header, hero, buttons).
- Use existing utility classes and component patterns (Tailwind utility classes, `.btn-primary` usage). Styling is not centralized in a CSS file—prefer modifying classes inline in HTML.
- Content sections follow a consistent pattern: section heading (h2), short description p, then cards/lists. See `index.html` and `README.md` section notes for example markup.

Concrete examples (search/replace patterns you may need)
- Change site name in header: modify the span with class `text-xl font-bold text-gray-900` in `index.html`.
- Update hero headline and subheading in `index.html` (the README notes approximate lines where these live).
- When adding a blog post, put the HTML file into `blog/` and update `blog.html` only if you need it listed — filenames must match the expected blog URL.

Integration points & external dependencies
- Tailwind and Font Awesome are loaded from CDNs; do not remove or replace without confirming how the site will be hosted.
- External links and contact endpoints (websitemarketinghq.com) are authoritative; update them only if the deployment or domain changes.

Safety rules for AI edits (must follow)
1. Never add or assume a backend API—this repo contains static HTML only. If a feature requires server-side logic, request clarification.
2. Preserve filenames and relative paths. Breaking a filename (or moving root HTML files) will break live URLs per `QUICK_START.md`.
3. Keep edits minimal and localized. Large refactors (adding build tooling or changing CSS architecture) require human approval.
4. When changing links, update every matching instance (header, hero CTAs, footer links). Use the README/QUICK_START as the source of truth.

Where to look for authority
- `README.md` — detailed maintenance guide with section locations and examples.
- `QUICK_START.md` — deployment instructions and canonical public URLs.
- `index.html`, `blog.html`, and the `blog/` directory — primary places to edit.

If unsure, ask these clarifying questions
- Should I change the deployed domain or keep `websitemarketinghq.com` in links?
- Is it acceptable to add a small build step (e.g., Tailwind CLI) if we want a more systematic styling workflow?

Short checklist for common tasks
- Update site copy: edit `index.html` and test locally in a browser.
- Add blog post: add file to `blog/` and verify URL `https://websitemarketinghq.com/blog/<filename>`.
- Update privacy/terms: edit `privacy.html` / `terms.html` and re-upload.

End of instructions — ask the repo owner if you need permission to introduce a build system or CI.
