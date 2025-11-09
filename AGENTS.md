# Repository Guidelines

## Project Structure & Module Organization
This Jekyll site keeps global settings in `_config.yml`, with main HTML entry points in `index.html` and `print.html`. Data that feeds templates belongs in `_data/data.yml`; this YAML file is the canonical source for the resume content and personal details shown across the site. Layouts live under `_layouts/` and reusable snippets in `_includes/` (component partials go in `_includes/partials/`). Styles are authored in `_sass/` and compiled through `assets/css/main.scss`; images, fonts, and downloads stay under `assets/`.

## Build, Test, and Development Commands
Run `bundle install` once to sync the gems pinned in `Gemfile.lock`. Use `bundle exec jekyll serve --livereload` for local authoring at `http://localhost:4000`, and `bundle exec jekyll build` to create the production `_site/` output. If Ruby is not installed locally, `docker-compose up` launches the same serve workflow inside a container.

## Coding Style & Naming Conventions
Indent Liquid, HTML front matter, and YAML with two spaces. Name Liquid collections descriptively (e.g., `experience_list`) and favor kebab-case for assets such as `assets/images/team-photo.jpg`. SCSS partials should begin with an underscore, live in `_sass/components/`, and be imported via `assets/css/main.scss` to preserve bundle order.

## Testing Guidelines
There is no automated test suite; rely on `bundle exec jekyll build` to catch Liquid or front matter issues before pushing. When editing `_data/data.yml`, spot-check the rendered pages or run `bundle exec jekyll serve` to confirm loops and includes resolve correctly. Document any manual validation of the print view in your PR notes.

## Commit & Pull Request Guidelines
Follow the repo history’s style: short, present-tense commit subjects (e.g., “Update experience timeline”). Group related template and data edits together. Pull requests should outline the user-visible change, list manual verification steps, link relevant issues, and include screenshots of updated sections or the print layout when visuals shift.

## Security & Configuration Tips
GitHub Pages deploys from the default branch; keep the root `CNAME` aligned with the live domain so Pages routes traffic to your custom hostname. Store contact details and social links in `_data/data.yml` to avoid inconsistent copies. If you add third-party scripts, document any required environment variables and note privacy implications in the PR description.
