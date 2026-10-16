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
  width, and long tags wrap within their column without reducing font sizes.
  No page or language is
  selected inside these components. The English documents retain their layout.

Both document versions use the same localized summary. Its `isShort` branch
links to the full PDF in the same language. The full document includes every
experience and the education section, with 15 pages in each language.

## Build

Prerequisites: GNU Make, XeLaTeX, latexmk, the Carlito font, and the custom
`chinjto-cv-resume` class from [toolbox-latex](https://github.com/chinjto/toolbox-latex).
The document Makefiles include `~/.make/latex.mk` from
[toolbox-make](https://github.com/chinjto/toolbox-make). The French documents also
use Babel's French support.

Run from the repository root:

```sh
make -C my-resume/documents/en/short build
make -C my-resume/documents/en/full build
make -C my-resume/documents/fr/short build
make -C my-resume/documents/fr/full build
```

Each build writes intermediate files to the document's `build/` directory and
copies the resulting PDF to `main.pdf` beside its source.

## French qualification references

The French documents explicitly mark all three qualifications as obtained, based
on the holder's confirmation. The CV shows bac+5, bac+3 and bac+2, without RNCP
references. The research below is retained as supporting documentation only.

- AFTI / ETGL (2015): *Expert en conduite et ingénierie de logiciel et système*,
  [RNCP21789](https://www.francecompetences.fr/recherche/rncp/21789/), level 7.
  The archived record cites the order of 9 January 2015, with effect from
  6 July 2013 through 30 January 2016. The later RNCP25531 title is not used.
- UPEC / BDISe (2013): *Licence professionnelle Systèmes informatiques et
  logiciels, spécialité Bases de données, Internet et sécurité*,
  [RNCP14686](https://www.francecompetences.fr/recherche/rncp/14686/), level 6.
  The historical title and its opening in 2009 are corroborated by the
  [AERES evaluation for 2013–2014](https://www.hceres.fr/sites/default/files/media/publications/rapports_evaluations/pdf/E2015-EV-0941111X-S3LP150008870-005254-RD.pdf).
- UPEC / DUT Informatique (2012): diploma name retained, level 5. The
  [RNCP20654 record](https://www.francecompetences.fr/recherche/rncp/20654/)
  confirms this qualification and level, but also cites the 2013 programme.
  Its precise applicability to the 2012 award has not been established, so no
  fiche number is assigned to this diploma in the CV.

Sources checked on 16 October 2026. No master grade or regulated engineering
degree is claimed for ETGL. The original English wording “localization fixes”
for Clear2Pay does not identify individual defects; the French wording therefore
keeps software localization distinct from workflow corrections, without naming
specific translations, locales or formats.
