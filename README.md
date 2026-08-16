# ttdne.github.io

Personal academic site of **Duong (Joe) Trinh** — AI Engineer at Viettel Cyber Security, research member at BKAI NLP Lab, HUST.

Built on [al-folio](https://github.com/alshedivat/al-folio) `v1.x`, a thin Jekyll starter whose runtime ships as versioned gems. Deployed to GitHub Pages by `.github/workflows/deploy.yml` on every push to `main`.

## Local development

```bash
bundle install
bundle exec jekyll serve      # http://localhost:4000/  (no baseurl -- this is a user page)
```

## Where things live

| What                          | File                                          |
| ----------------------------- | --------------------------------------------- |
| Bio, profile photo, front page| `_pages/about.md`, `assets/img/prof_pic.jpg`  |
| CV contents                   | `_data/cv.yml` (rendered by `_pages/cv.md`)   |
| CV PDF                        | `assets/pdf/CV_LangAGI.pdf`                   |
| Publications                  | `_bibliography/papers.bib`                    |
| News items on the front page  | `_news/`                                      |
| Project pages                 | `_projects/`                                  |
| Blog posts                    | `_posts/`                                     |
| Social links                  | `_data/socials.yml`                           |
| Site-wide settings            | `_config.yml`                                 |
| Theme colour (Tiffany blue)   | `_sass/_variables.scss`, `_sass/_themes.scss`  |
| Any other custom CSS          | `_sass/_custom.scss` (ours alone, loaded last) |

`_sass/_variables.scss`, `_sass/_themes.scss` and `assets/css/main.scss` are **local overrides** of files owned by the `al_folio_core` gem. Each is a verbatim copy with the changed lines flagged in a comment. `_sass/_custom.scss` is not an override — it is ours, and it is where new CSS should go. After a gem update, check the three overrides for drift:

```bash
bundle exec al-folio upgrade overrides audit
bundle exec al-folio upgrade overrides diff _sass/_variables.scss
```

See [`AGENTS.md`](AGENTS.md) and [`docs/`](docs/) for the upstream architecture notes.
