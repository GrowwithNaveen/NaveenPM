# Naveen’s Portfolio

A dependency-free static portfolio built with HTML, CSS, and browser JavaScript. It has no build step or package manager, and can be served directly by Vercel.

## Project structure

- `index.html`, `projects.html`, `project.html`, `tenets.html`, `audiophile.html`, and `bookshelf.html` are the page shells.
- `data.js` contains portfolio content, project details, navigation data, and personal-page content.
- `app.js` renders shared navigation and page content, including the detailed case-study layouts.
- `styles.css` contains the shared design system, responsive layouts, and light/noir themes.
- `assets/` contains portraits, project banners, and other images. Theme-specific project images use `-light` and `-dark` filenames.
- `vercel.json` configures clean URLs for deployment.

## Edit and preview

1. Update copy and structured content in `data.js`.
2. Update page composition and interactions in `app.js`.
3. Update visual styles in `styles.css`.
4. Put images in `assets/` and reference them with relative paths.
5. Preview locally by opening `index.html`, or from this folder run `python3 -m http.server 8000` and visit `http://localhost:8000` for a closer match to deployment.

There are no external runtime libraries. The Google Fonts stylesheet is optional; system fonts remain as fallbacks.

## Recommended update workflow

Use the local folder for normal edits, and treat GitHub as the shared source of truth:

1. Make and review changes locally.
2. Commit the finished change to a feature branch, then merge it into `main` when ready.
3. Connect the GitHub repository to Vercel. Vercel will create preview deployments for branches and update the production deployment when `main` changes.
4. Keep direct edits in GitHub for small, urgent changes only, then pull those changes back into the local folder before continuing.

This keeps the local copy, GitHub history, and deployed site aligned. Vercel can assign a stable `*.vercel.app` production address; a custom domain can be attached later in the Vercel project settings.

## Vercel deployment settings

- Framework preset: **Other** (static site)
- Root directory: repository root
- Build command: none
- Output directory: repository root/default static output
- Install command: none

`vercel.json` enables clean URLs and disables trailing slashes. The site uses relative links and project IDs in the query string, so case-study links work without a build step.
