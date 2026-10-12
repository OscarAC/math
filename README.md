# Solutions to Selected Exercises from Math Books

Worked solutions I write while studying, organized as one directory per book.
Read them online at <https://oscarac.github.io/math/>.

Each chapter is a standalone document that can be read without building
anything: a [Tern](https://github.com/OscarAC/tern) page, `chapterN.html`, that
renders in the browser, or, for the chapters not yet moved to Tern, a LaTeX
document compiled to a PDF.

These are my own solutions, written as part of learning the material. They are
unofficial and may contain errors, corrections are welcome.

## Books

| Book                                                                                                       | Online                                                   | Source license             | Source files                                       |
| ---------------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | -------------------------- | -------------------------------------------------- |
| [_Book of Proof_, Richard Hammack (ed. 2.2)](BookOfProof_Hammack/)                                         | [solutions](https://oscarac.github.io/math/#hammack)     | CC BY-ND 3.0               | `chapterN.html`                                    |
| [_Algebra: An Elementary Text-Book_, G. Chrystal, Part I (1886)](Algebra_Chrystal/)                        | [solutions](https://oscarac.github.io/math/#chrystal)    | public domain              | `chapterN.html`                                    |
| [_A Treatise on Plane Trigonometry_, E. W. Hobson (ed. 7, 1928)](PlaneTrigonometry_Hobson/)                | not yet                                                  | public domain              | `chapterN.tex` / `chapterN.pdf`                    |

## Building

Each LaTeX chapter compiles independently:

```sh
pdflatex chapterN.tex
```

`template.sty` lives at the repository root and is symlinked into each book
directory, so this works from inside the book directory with no `TEXINPUTS`
juggling.

The Tern pages need no build: open one in a browser. They share the vocabulary
and style in `tern/`, and `tern check chapterN.html` reports any mistakes.

## Publishing

GitHub Pages serves the root of `main` as it is (`.nojekyll` turns off Jekyll),
with `index.html` as the front page linking every chapter.

## Attribution

Exercise statements are quoted from the respective books; see each book's
README for its attribution and license details. The solutions themselves,
the answers, derivations, and surrounding prose are my own work. Licensing
is per book; [LICENSE.md](LICENSE.md) explains the scheme.
