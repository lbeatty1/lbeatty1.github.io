# CLAUDE.md

Guidance for working on this site with Claude Code.

## What this is

Personal academic website for Lauren Beatty, built on **academicpages** (a fork of the
Minimal Mistakes Jekyll theme) and deployed via **GitHub Pages**. Pushing to `master`
triggers GitHub's own Jekyll build with the `github-pages` gem; there is no separate deploy
step. Content lives in the same files the template ships, so edits are made in place rather
than through a plugin.

## Local preview

Ruby 3.2.11 is installed at `C:\Ruby32-x64`. The site serves at `localhost:4000` (Lauren's
own terminal) or `localhost:4001` (Claude's preview, below).

### Lauren's own terminal (PowerShell)

```powershell
cd C:\Users\laure\Documents\lbeatty1.github.io
bundle exec jekyll serve --force-polling --livereload
```

Then open http://localhost:4000. Edits to pages, `_data/`, and CSS hot-reload on save.

### Claude's in-chat preview (preview MCP)

Use this to screenshot pages and verify changes without Lauren doing anything. Config lives
in `.claude/launch.json` (server name `jekyll-preview`, port 4001).

1. `preview_start` with name `jekyll-preview` → returns a `serverId`.
2. `preview_screenshot` with that `serverId`. The **first** screenshot after start/navigate
   is often blank (first request triggers a build; the theme fades content in via JS) —
   take a second shot, or `curl` the page first to warm it.
3. Navigate between pages with `preview_eval`: `window.location.assign('http://127.0.0.1:4001/research/')`.

If running `bundle`/`jekyll` directly from a non-interactive shell (not via the launch
config), first put Ruby on PATH for that call:

```powershell
$env:Path = [Environment]::GetEnvironmentVariable("Path","Machine") + ";" + [Environment]::GetEnvironmentVariable("Path","User")
```

Why the launch command is shaped the way it is: bundler's `exec` looks up the `jekyll`
binstub on **PATH**, so the command both `cd`s into the project (to find the Gemfile) and
prepends `C:\Ruby32-x64\bin` to PATH. Dropping either piece gives
`bundler: command not found: jekyll`.

## Windows / Ruby gotchas

- **`_config.yml` is not hot-reloaded.** Changing it (e.g. the sidebar title) requires
  stopping and restarting the server. All other content reloads on save.
- **`wdm` is commented out in the `Gemfile`.** It won't compile on Ruby 3.2+, so file
  watching uses `--force-polling` instead. The `wdm` line is Windows-only and has no effect
  on the GitHub Pages (Linux) build.
- **Don't use `jekyll serve --detach`.** It calls `fork()`, which Windows Ruby doesn't
  implement. Run the server in the background instead.
- **Stale-gem errors from `bundle install`** (e.g. a yanked `nokogiri`): delete
  `Gemfile.lock` and rerun. The lockfile is regenerated against current versions.

## Where things live

- **Pages:** `_pages/` — `about.md` (home, permalink `/`), `research.md`, `other.md`,
  `cv.md` (unlinked; nav points straight at the PDF), `teaching.md` (commented out of nav).
- **Navigation:** `_data/navigation.yml`. The `CV` link points directly to
  `/files/CVBeatty.pdf`.
- **Author block / sidebar:** `_config.yml` under `author:`. The `bio` field is the small
  title under the name in the sidebar (currently "Economist").
- **PDFs and other files:** `files/` → served at `/files/...`.
- **Section-header styling:** custom rule in `assets/css/main.scss` (`.archive > h2`) gives
  content section headers an underline and larger size so they outrank the bold paper titles.

## Formatting conventions

- **Papers and policy writing**  style: a **bold, quoted**
  title, then `With <coauthors>.`, a status (`Submitted` / `Draft Available Upon Request`)
  or outlet/date, and `Available on [SSRN](<doi>)` when there's a link. Lauren is dropped
  from the "With" list.
- **Section headers** use `##`. To hide a page's `<h1>` title (as on Research/Other), set
  `title: ""` in front matter — `_layouts/archive.html` guards the heading with
  `{% if page.title %}`.

