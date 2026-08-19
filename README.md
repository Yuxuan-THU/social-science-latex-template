# Social Science LaTeX Template

A clean, reproducible **XeLaTeX** template for social science papers —
built for journals that want professional typesetting without the pain.

**English-first, Chinese-ready.** Times-like fonts, publication-quality
tables, TikZ figures, author–year citations — all in one drop-in skeleton.

---

## ✨ Highlights

- **Professional layout** — Times (`newtxtext`/`newtxmath`), 1-inch margins,
  1.35 line spacing, standard 12pt manuscript format
- **Bilingual-ready** — full CJK support via `xeCJK`; English first,
  Chinese paragraphs whenever you need them (auto-detects system fonts:
  SimSun on Windows, Noto CJK on macOS/Linux)
- **Journal-style tables** — `booktabs` + `threeparttable` + `makecell`,
  with auto-fitting wide tables (`adjustbox`)
- **Reproducible figures** — every figure is a standalone TikZ source that
  compiles to a PDF; regenerate anytime, no hand-edited images
- **Harvard citations** — `natbib` + AEA-style `.bst`; add entries to one
  `references.bib` (UTF-8, Chinese entries supported)
- **Organized by section** — one file per section under `text/`; tables and
  figures in their own folders; appendix numbering handled for you

## 🚀 Quick start

```bash
xelatex main.tex
bibtex  main
xelatex main.tex
xelatex main.tex
```

Or with `latexmk`:

```bash
latexmk -xelatex main.tex
```

**Overleaf:** upload as a zip → set compiler to **XeLaTeX** → done.

> A compiled preview is included as [`main.pdf`](main.pdf).

## 📁 Structure

```
.
├── main.tex                 # root: title, sections, appendix
├── A_PreambleSettings.tex   # one place for all global settings
├── references.bib           # bibliography (UTF-8, Chinese OK)
├── aeaown.bst               # Harvard (author–year) style
├── text/                    # one file per section
├── tables/                  # table files
└── figures/                 # TikZ source + compiled PDF, same name
```

## ✏️ Make it yours

1. **Title & authors** — edit `\title{...}` / `\author{...}` in `main.tex`
2. **Content** — replace the placeholder files under `text/`
3. **Tables** — drop files in `tables/`, `\input` them where needed
4. **Figures** — add `figures/my-figure.tex`, compile to
   `my-figure.pdf`, include with `\includegraphics{my-figure.pdf}`
5. **Fonts** — switch CJK fonts in `A_PreambleSettings.tex`

## 📄 License

MIT — use it, change it, ship it.

---

*Made for researchers who want to spend time on the science,
not the typesetting.*
