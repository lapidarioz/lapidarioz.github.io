# rafaeltesta.org

Personal website for Rafael Luiz Testa, PhD, built with Jekyll and the
[al-folio](https://github.com/alshedivat/al-folio) v1.1 starter architecture.

## Site structure

- `_pages/` contains the homepage, About, Projects, Publications, CV, and 404 pages.
- `_projects/` contains the four detailed selected-work narratives.
- `_bibliography/papers.bib` drives both the Publications page and selected publications on the homepage.
- `_data/cv.yml` and `_data/socials.yml` contain structured CV and public profile data.
- `_sass/_custom.scss` is the site-specific visual layer; `assets/css/main.scss` imports it after the al-folio styles.

The installed al-folio release uses version-pinned plugin gems. Keep `Gemfile` and the
`plugins` list in `_config.yml` aligned when changing plugin dependencies.

## Local development

The recommended path is Docker:

```sh
docker compose up
```

The site is served at `http://localhost:8080`.

For a native Ruby environment:

```sh
bundle install
npm ci
bundle exec jekyll serve
```

## Validation

```sh
npm run lint:prettier
bundle exec al-folio upgrade audit --no-fail
bundle exec al-folio upgrade overrides audit
bundle exec jekyll build
```

The GitHub Actions deployment builds the site from `master` and publishes the generated
`_site` directory to `gh-pages`. The repository must keep GitHub Pages pointed to the
`gh-pages` branch and retain the custom domain `rafaeltesta.org`.

## Content guardrails

The current project diagrams are conceptual process diagrams, not experimental results.
Add real comparison images, plots, short videos, or a PDF CV only when verified source files
are available. Do not add confidential system details or unsupported performance claims.
