# What This Repo Is

This entire repo is the **source for the second-hand-tigers organization's
GitHub Pages website**, published at `https://second-hand-tigers.github.io`.
Unlike other repos in this organization, there's nothing else here — no
Wiki, no `/slides`, no project content — because this repo's only purpose
is to be the site. The root of the repo *is* the site source, rather than
living in a `docs/` subfolder the way a project's Pages site does inside
its own repo.

## Why This Repo's Root Is the Source (No `docs/` Folder Here)

A repo whose Pages source is set to "Deploy from a branch" can only serve
from the repo root or from a folder named `docs`. Project repos in this
organization (which also carry a README, Wiki, etc.) use `docs/` to keep
the site source visually separate from everything else in the repo. This
repo has nothing else to separate it from, so the root is simpler and was
chosen instead — same underlying platform rule, different practical
choice given what's actually in each repo.

## Why This Repo Is Named `second-hand-tigers.github.io`

An organization's (or user's) top-level Pages site — the one published
at the account's root domain rather than a subpath — requires a repo
named *exactly* `<account-name>.github.io`. This is a one-per-account,
permanent name, unlike a project site's repo, which can be named
anything and still get a Pages site at `<account>.github.io/<repo-name>`.

## Files Currently In Use Here

| File | Purpose |
|---|---|
| `_config.yml` | Site-wide settings: title, description, and which built-in theme to use (`theme: jekyll-theme-cayman`, etc.). One of GitHub's 13 supported themes — changing themes is a one-line edit here, no other files need to change. |
| `index.md` | The site's only page currently: the org-wide "Learning Hub" home page. Front matter at the top (`layout: default`, `title: ...`) plus the page content in Markdown below it. All links on this page use full `https://github.com/...` URLs rather than relative links, since this site lives on a different domain than the repos it points to. |

Every content page here needs `layout: default` in its front matter —
that's the one layout name guaranteed to exist across all of GitHub's
supported themes, so pages keep working correctly if the theme in
`_config.yml` ever changes.

## Other Files You Might Add Later

None of these exist yet, but they're standard parts of a Jekyll/GitHub
Pages site and may show up here as this site grows:

| File / Folder | Purpose |
|---|---|
| `assets/css/style.scss` | Custom CSS overrides layered on top of the chosen theme (e.g. shrinking a banner's padding) without abandoning the theme itself. Must start with an empty `---` front-matter block, then `@import "{{ site.theme }}";`, then your overrides. |
| `assets/images/`, `assets/` (general) | Images or other static files the site references — logos, screenshots, downloadable files linked from a page. |
| `_layouts/` | Custom page layouts, if the built-in theme layouts (`default`, etc.) stop being enough. |
| `_includes/` | Reusable snippets of HTML/Markdown pulled into multiple pages (a shared header, footer, or nav block), instead of copy-pasting the same content everywhere. |
| `_data/` | Structured data (YAML/JSON/CSV) a page can loop over — e.g. a growing Topic Areas list rendered from data instead of hand-written Markdown. |
| Additional `.md` pages | Each new top-level page (e.g. a dedicated "How to Contribute" page) is just another `.md` file here with its own front matter and `permalink`. |
| `favicon.ico` | The small icon shown in a browser tab for this site. |
| `CNAME` | Only needed if this site is ever pointed at a custom domain instead of `second-hand-tigers.github.io`. |

## Navigation Convention Used On This Site

This site's home page carries only a "Toggle to Repo View" link (pointing
to `https://github.com/second-hand-tigers`) at the top — no "up" breadcrumb,
since the org is the top of this organization's site hierarchy and there's
nothing above it to link to. Project sites one level down (e.g.
`badocter-career-learnings`, `career-learnings-directory`) follow the
fuller pattern: an italicized breadcrumb (or stacked breadcrumb lines,
using `<br>`) pointing up to their parent, plus a labeled toggle to that
same page's GitHub-repo equivalent. New pages added here should stay
consistent with whichever part of that pattern applies to their level.
