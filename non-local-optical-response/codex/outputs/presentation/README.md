# Mesoscopic and nonlocal optical response — journal-club deck

This folder is the complete source bundle for the talk:

- `presentation.tex` — Beamer source for the slides.
- `presentation.pdf` — compiled 29-slide deck.
- `references.bib` — retained as a source index, but not used to generate a presentation bibliography.
- `assets/` — downloaded or rendered source figures used by the deck, including the actual Fig. 1–3 assets from review reference [1] and literature figures used throughout the historical development.
- `sources.md` — figure provenance, URLs, and usage notes.
- `paper_citations.md` — compact slide-style citations paired with stable paper links.

The deck follows a historiographic path from local Maxwell electrodynamics through microscopic quantum calculations, Feibelman surface response, spill-out, and hydrodynamic models to the spherical SC–HDM integral formulation. Borrowed figures carry compact bracketed citations directly on their slides; there is no bibliography section.

## Build

From this directory, a standard build is:

```sh
pdflatex presentation.tex
pdflatex presentation.tex
```

The PDF in this bundle was compiled with a user-space TeX Live setup and checked with `pdfinfo`, `pdftotext`, and rendered-page visual inspection. Standard LaTeX auxiliary files are retained so the deck can be rebuilt or debugged.

## Figure policy

The review PDF contains no embedded raster figures (`pdfimages -list` returned none). The presentation therefore combines:

1. figures obtained from papers in the review bibliography, including the actual Figures 1–3 from review reference [1];
2. compact bracketed citations on every slide containing a borrowed figure;
3. original TikZ only where it still serves as connective exposition rather than a substitute for a published result.

Two review-page renders are retained in `assets/` as an audit trail but are not displayed in the talk.
