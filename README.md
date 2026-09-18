# Brady Allardice — academic website

Built with the [HugoBlox Academic CV](https://github.com/HugoBlox/hugo-theme-academic-cv) template
(Hugo, MIT license) and deployed to GitHub Pages by GitHub Actions on every push to `main`.

## Where the content lives

| What | File |
|---|---|
| Name, bio, photo links, education, experience, skills, awards, languages | `data/authors/me.yaml` |
| Profile photo | `assets/media/authors/me.jpg` (any `me.*` image works) |
| CV PDF | `static/uploads/allardice_cv.pdf` (replace the file, keep the name) |
| Home page sections and their order | `content/_index.md` |
| Experience page | `content/experience.md` |
| Papers and reports (one folder each) | `content/publications/<slug>/index.md` |
| Talks | `content/events/<slug>/index.md` |
| News items | `content/news/<slug>.md` |
| Menu | `config/_default/menus.yaml` |
| Site name, colours, fonts, footer | `config/_default/params.yaml` |

### Adding a paper

Copy an existing folder in `content/publications/`, rename it, and edit the front matter.
`publication_types` decides which home-page list it appears in:

- `article` → Working Papers
- `manuscript` → Work in Progress
- `report` → Policy Reports
- `paper-conference` / `article-journal` → published work (add a matching list in `content/_index.md`)

Put a PDF named after the folder, or a `cite.bib`, in the same folder and the theme links it automatically.
You can also add links (PDF, SSRN, code, slides) under `links:` in the front matter.

### Adding news or a talk

Copy any file in `content/news/` or any folder in `content/events/` and edit the title and date.
These appear only as list entries on the home page; they do not get their own pages.

## Local preview

Requires Hugo **extended 0.161.1**, Go, and Node 22 with pnpm:

```
pnpm install
hugo server
# open http://localhost:1313/
```

## Deployment

1. Push `main` to GitHub.
2. Repository **Settings → Pages → Build and deployment → Source: GitHub Actions**.
3. The `Deploy website to GitHub Pages` workflow builds and publishes the site to
   `https://bradyallardice.github.io/` (the repository is named `bradyallardice.github.io`,
   which GitHub serves at the root of the user domain).

## Notes

- **Hugo version is pinned to 0.161.1** in `hugoblox.yaml` (the workflow reads it from there).
  With the template's default 0.162.0, the build fails on any page with `links:` in its front matter
  (`assignment to entry in nil map` in the theme's `functions/build_links.html`). Re-test locally before bumping.
- `layouts/_partials/views/date-title-summary.html` is a local copy of a theme file, changed so that
  news and talk entries (which have no page of their own) are shown without a link or "Read more".
- The template's weekly auto-upgrade workflow was intentionally not included, so theme updates happen only
  when you choose to run them.
