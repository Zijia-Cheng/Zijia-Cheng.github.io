# AGENTS.md

## Project overview
- This repository is a personal academic website built with Jekyll on top of the `academicpages` / `minimal-mistakes` structure.
- Content is primarily authored in Markdown with YAML front matter and rendered through Jekyll collections and layouts.
- Ruby/Bundler powers site generation; `npm` is only used to rebuild minified JavaScript assets.

## Repository layout
- `_pages/`: standalone site pages such as `about`, `cv`, `publications`, and archives.
- `_posts/`: dated blog posts; filenames follow `YYYY-MM-DD-slug.md`.
- `_talks/`, `_publications/`, `_teaching/`, `_portfolio/`: Jekyll collections with one Markdown/HTML file per entry.
- `_layouts/`, `_includes/`, `_sass/`, `assets/`: theme templates and styling/assets.
- `images/` and `files/`: static assets referenced by content pages.
- `markdown_generator/`: notebook and Python utilities that generate collection Markdown from TSV/Bib inputs.

## Core workflows
- Install site dependencies with `bundle install`.
- Run the site locally with `bundle exec jekyll serve`.
- If `_config.yml` changes, restart `jekyll serve`; Jekyll does not hot-reload that file.
- If editing JavaScript under `assets/js/`, rebuild the minified bundle with `npm run build:js`.
- Do not hand-edit `assets/js/main.min.js` unless there is a strong reason; prefer changing source files and rebuilding.

## Editing conventions
- Preserve YAML front matter formatting and required keys for each content type.
- Follow existing filename patterns, especially for dated content in `_posts/`, `_talks/`, and `_publications/`.
- Keep permalinks collection-specific and consistent with existing entries.
- Prefer Markdown for content changes; only use raw HTML when the page already relies on it or layout control is necessary.
- Keep changes focused and avoid unnecessary theme-wide refactors when updating content.
- Match the surrounding style of the touched file instead of introducing a new structure or tone.

## Collection guidance
- `_posts/`: include `title`, `date`, `permalink`, and relevant `tags`; keep post body self-contained and reference images with repo-relative paths already used in the site.
- `_pages/`: preserve top-level routing fields such as `permalink`, `title`, and `author_profile` when present.
- `_talks/`, `_publications/`, `_teaching/`: use front matter keys already established in nearby entries, such as `collection`, `type`, `venue`, `date`, `location`, `paperurl`, and `citation`.
- For bulk talk/publication updates, prefer the scripts/notebooks in `markdown_generator/` over manually creating many similar files.

## Validation
- For content-only edits, a local `bundle exec jekyll serve` sanity check is usually sufficient.
- For JavaScript edits, run `npm run build:js` after modifying sources.
- There is no dedicated automated test suite in this repository; validate by building or serving the site when practical.

## Safety notes
- Do not commit secrets, tokens, or private analytics identifiers into `_config.yml`.
- Be careful with generated or platform-specific junk files such as `.DS_Store`; avoid adding them to commits.
- When modifying theme files in `_layouts/`, `_includes/`, or `_sass/`, keep compatibility with existing collection pages and front matter assumptions.
