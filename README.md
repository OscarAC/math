# Solutions to Selected Exercises from Math Books

Worked solutions I write while studying, organized as one directory per book.
Each chapter is a standalone LaTeX document compiled to a PDF, so the solutions
can be read without building anything.

These are my own solutions, written as part of learning the material. They are
unofficial and may contain errors, corrections are welcome.

## Books

| Book                                                                                                       | Source license             | Source files                    |
| ---------------------------------------------------------------------------------------------------------- | -------------------------- | ------------------------------- |
| [_Book of Proof_, Richard Hammack (ed. 2.2)](BookOfProof_Hammack/)                                         | CC BY-ND 3.0               | `chapterN.tex` / `chapterN.pdf` |
| [_Algebra: An Elementary Text-Book_, G. Chrystal, Part I (1886)](Algebra_Chrystal/)                        | public domain              | `chapterN.tex` / `chapterN.pdf` |

## Building

Each chapter compiles independently:

```sh
pdflatex chapterN.tex
```

`template.sty` lives at the repository root and is symlinked into each book
directory, so this works from inside the book directory with no `TEXINPUTS`
juggling.

## Attribution

Exercise statements are quoted from the respective books; see each book's
README for its attribution and license details. The solutions themselves,
the answers, derivations, and surrounding prose are my own work. Licensing
is per book; [LICENSE.md](LICENSE.md) explains the scheme.
