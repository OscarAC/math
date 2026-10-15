# ozkr.ac

The source of <https://ozkr.ac>: my home page, projects, blog and wiki. Every
page is a [Tern](https://github.com/OzkrAC/tern) note, an `.html` file that
renders itself in the browser, and GitHub Pages serves `main` as it is
(`.nojekyll` turns off Jekyll; nothing is built).

| Path                                  | What                                                                                                                                                                                                |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `index.html`                          | the home page                                                                                                                                                                                       |
| `wiki/`                               | what I write while studying, by subject; [`wiki/math/`](wiki/math/) holds the worked solutions, with its own README and LICENSE                                                                     |
| `projects/`                           | the portfolio                                                                                                                                                                                       |
| `blog/`                               | posts, `blog/<slug>.tern.html`; `blog/index.html` lists them newest first from the catalogue (`::notes`)                                                                                             |
| `lib/`                                | what every page shares: `math.js`, the vocabulary (exercises, theorems, proofs, callouts); `site.js`, the masthead, the footer and the colour-scheme switch; `site.css`, the look; the logo `ozkrac.png` |
| `*/notes.json`, `*/search.json`       | written by `tern index`, never by hand: the catalogue a section's `::notes` lists and the index its `::search` reads (`wiki/`, `blog/`)                                                              |
| `.githooks/`                          | the git hooks (below)                                                                                                                                                                               |
| `404.html`                            | the not-found page; its paths start with `/`, as it is served at any address                                                                                                                        |
| `CNAME`                               | the custom domain, `ozkr.ac`                                                                                                                                                                        |
| `favicon.ico`, `apple-touch-icon.png` | the site icons, from the logo; browsers ask for both at the root, so no page links them                                                                                                             |

Every page loads `tern.js` and its add-ons from jsDelivr at one tag, `v0.4.2`:
the release the Tern checkout that runs the hooks is at, since `tern index`
writes files for its own series. Bump them together.

`ozkr.ac/tern/` is not in this repository: it is the Tern repository's own
Pages site, which GitHub serves under this domain. Keep the root free of a
`tern/` folder.

Chapter notes (`*notes.tern.html`) are kept beside their chapters and are
gitignored: they stay private, and the hooks never index them.

## Committing

Once per clone, point git at the hooks:

```sh
git config core.hooksPath .githooks
```

Before every commit, `.githooks/pre-commit` checks the tracked notes
(`tern check --fail-on=warning`) and writes the catalogue and search index of
each section again, staging them; a merge commit runs the same through
`pre-merge-commit`. The same by hand:

```sh
tern check . --fail-on=warning
tern index wiki -o wiki
tern index blog -o blog
```

The solutions' licensing is explained in [`wiki/math/LICENSE.md`](wiki/math/LICENSE.md).
