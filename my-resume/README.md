# Resume (LaTeX)

The resume is available in English (`en`) and French (`fr`), with a one-page
`short` version and a complete `full` version for each language.

| Language | Short | Full |
| --- | --- | --- |
| English | [PDF](documents/en/short/main.pdf) | [PDF](documents/en/full/main.pdf) |
| Français | [PDF](documents/fr/short/main.pdf) | [PDF](documents/fr/full/main.pdf) |

## Source layout

- `documents/{en,fr}/{short,full}/main.tex`: document entry points, each with its
  own `Makefile` and `.env` build configuration.
- `sections/{en,fr}/global/`: localized summary and education sections.
- `sections/{en,fr}/works/`: localized professional experience sections.
- `profile/my-data.tex`: shared links, independent of the document language.
- `assets/`: shared images.
- `layout/adaptive.tex`: optional generic layout adaptations used by the French
  documents. Contact labels and skill names wrap, job columns use their enclosing
  width, long tags fit within their column, and page bodies scale down only when
  necessary to preserve the explicit page boundaries. No page or language is
  selected inside these components. The English documents retain their layout.

Both document versions use the same localized summary. Its `isShort` branch
links to the full PDF in the same language. The full document includes every
experience and the education section, keeping the same page breakdown in both
languages (15 pages).

## Build

Prerequisites: GNU Make, XeLaTeX, latexmk, the Carlito font, and the custom
`chinjto-cv-resume` class from [toolbox-latex](https://github.com/chinjto/toolbox-latex).
The document Makefiles include `~/.make/latex.mk` from
[toolbox-make](https://github.com/chinjto/toolbox-make). The French documents also
use Babel's French support and `adjustbox`.

Run from the repository root:

```sh
make -C my-resume/documents/en/short build
make -C my-resume/documents/en/full build
make -C my-resume/documents/fr/short build
make -C my-resume/documents/fr/full build
```

Each build writes intermediate files to the document's `build/` directory and
copies the resulting PDF to `main.pdf` beside its source.
