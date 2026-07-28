# Information and Decision Sciences PhD Program (Public Site)

[Carlson School of Management](https://carlsonschool.umn.edu/), [University of Minnesota](https://twin-cities.umn.edu/)

This repository is a public, GitHub-based website providing supplemental information and FAQs for prospective students interested in the Information and Decision Sciences PhD program at the Carlson School of Management, University of Minnesota.

This site is **not official** — see the disclaimer on the site itself. It exists to give prospective students context and orientation that complements, rather than duplicates, the official Carlson School admissions pages (see `docs/official-resources.md`).

## Local setup

```bash
python3 -m venv venv
source venv/bin/activate       # on Windows: call activate-python.bat
pip install -r requirements.txt
```

## Preview

```bash
source venv/bin/activate
mkdocs serve
```

Then open <http://127.0.0.1:8000/> in a browser. The site reloads automatically as you edit files under `docs/`.

## Build

```bash
mkdocs build --strict
```

`--strict` fails the build on broken internal links or config warnings — run this before publishing any change.

## Deploy

The site is published to **GitHub Pages** from the `gh-pages` branch:

```bash
mkdocs gh-deploy
```

This builds the site and pushes it to the `gh-pages` branch of this repository. GitHub Pages must be configured (once) in the repo's Settings → Pages to serve from the `gh-pages` branch. After the first deploy, the site is available at <https://de4liu.github.io/ids-phd-public/>.

## Updating content

All page content lives in `docs/` as plain Markdown — no build tooling knowledge is required beyond the commands above:

- `docs/index.md` — Home page.
- `docs/considering-the-phd.md` — the "Considering the Information and Decision Sciences PhD?" resource/FAQ.
- `docs/official-resources.md` — curated links to official Carlson/UMN pages. Update this first whenever an official URL changes.

When editing:

- **Do not restate facts that change year to year** (deadlines, funding amounts, test-score minimums, faculty rosters) — link to the official Carlson/UMN page instead, so this site can't go stale on exactly the things prospective students most need to be current.
- **Do not include private or individual contact information**, internal procedures, or evaluative language intended for faculty/committee use (e.g. content from the internal PhD Handbook or admissions correspondence templates). This site is public.
- Run `mkdocs build --strict` and skim the rendered `site/` output (or `mkdocs serve`) before committing.

## Project layout

    mkdocs.yml              # Site configuration, navigation, theme.
    docs/
        index.md            # Home page.
        considering-the-phd.md
        official-resources.md
        stylesheets/extra.css   # Understated Carlson maroon/gold accent colors.
    requirements.in / requirements.txt   # Pinned Python dependencies (mkdocs-material).

## Commands

* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.
* `mkdocs gh-deploy` - Deploy the site to GitHub Pages.
