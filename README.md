# Political Science LaTeX Template (English–Chinese Bilingual)

A clean, reproducible LaTeX template for political science manuscripts,
derived from a real working paper project. English-first, with full Chinese
(CJK) support. Compiles with **XeLaTeX + BibTeX**.

中文政治学论文 LaTeX 模板（英文为主、中文为辅，XeLaTeX + xeCJK 编译）。

## Features

- **Bilingual typesetting** — English main text with optional Chinese
  paragraphs, abstract, and comments (XeLaTeX + `xeCJK`).
- **Times-like fonts** — `newtxtext` / `newtxmath` for text and math.
- **Publication-quality tables** — `booktabs`, `threeparttable`, `makecell`,
  `adjustbox` (auto-fit wide tables).
- **Figures with a reproducible workflow** — the standalone TikZ source
  and its compiled PDF live side by side in `figures/` with the same file
  name, and are included directly with `\includegraphics`.
- **Author–year citations** — `natbib` with a Harvard style
  (`aeaown.bst`, AEA style).
- **Math & theorems** — `amsmath`, `amssymb`, `amsthm` environments
  (theorem, lemma, proposition, assumption, hypothesis, …).
- **Appendix support** — table/figure numbering restarts with `B`/`A`
  prefixes.
- **Cross-platform CJK fonts** — auto-selects SimSun/SimHei (Windows),
  Noto CJK (macOS/Linux), with fake-bold for Chinese bold text.

## Requirements

- A TeX distribution with **XeLaTeX**: TeX Live (macOS/Linux) or MiKTeX
  (Windows).
- A CJK font installed on your system:
  - Windows: SimSun / SimHei / FangSong (built in)
  - macOS: Songti SC / Heiti SC (built in), or install Noto CJK
  - Linux: `fonts-noto-cjk` package
- `bibtex` (included in all TeX distributions).

## Quick start

### Compile from the command line

```bash
xelatex main.tex
bibtex  main
xelatex main.tex
xelatex main.tex
```

or, if you have `latexmk`:

```bash
latexmk -xelatex main.tex
```

### Overleaf

1. New project → Upload → upload this folder as a zip.
2. Set the compiler to **XeLaTeX** (Menu → Compiler → XeLaTeX).
3. If the main file is not auto-detected, set **main.tex** as the root file.
4. If Chinese fonts are missing on Overleaf, install/select a CJK font
   (Overleaf offers Noto Serif CJK SC, FandolSong, etc.). You can hard-code
   the font in `A_PreambleSettings.tex`.

## Project structure

```
.
├── main.tex                     # root file: title, structure, appendix
├── A_PreambleSettings.tex       # global preamble (fonts, margins, tables, math, citations)
├── aeaown.bst                   # Harvard (author–year) bibliography style
├── references.bib               # bibliography database (UTF-8; Chinese OK)
├── latexmkrc                    # latexmk config (xelatex + bibtex)
├── text/                        # section files
│   ├── abstract.tex
│   ├── introduction.tex
│   ├── conclusion.tex
│   ├── THE ARGUMENT/            # theory sections
│   ├── HISTORICAL BACKGROUND/   # background sections
│   ├── RESEARCH DESIGN/         # data & methods sections
│   ├── RESULTS/                 # results & robustness sections
│   └── APPENDIX/                # appendix tables/figures lists
├── tables/                      # table files (booktabs + threeparttable)
└── figures/                     # figure files: TikZ source + compiled
    ├── example-figure.tex       #   PDF side by side (same file name)
    └── example-figure.pdf
```

## How to customize

1. **Title & authors** — edit the `\title{...}` / `\author{...}` block in
   `main.tex`.
2. **Sections** — edit the files under `text/`; add/remove `\section` /
   `\subsection` entries in `main.tex` and keep one file per section.
3. **Tables** — put table files in `tables/` and `\input` them from
   `text/APPENDIX/tables.tex` (or directly in a section).
4. **Figures** — put the standalone TikZ source and its compiled PDF side
   by side in `figures/` with the same file name (e.g.,
   `figures/my-figure.tex` → `figures/my-figure.pdf`), and include it with
   `\includegraphics{my-figure.pdf}` (`\graphicspath` is set to `{figures/}`).
   Figures produced by external software (Stata/R/Python exports,
   screenshots) need no source file — just drop the PDF in `figures/`.
5. **CJK fonts** — edit the font block at the top of
   `A_PreambleSettings.tex`.
6. **Bibliography** — add entries to `references.bib` and cite with
   `\citep{key}` / `\citet{key}`.

## Notes / tips

- The placeholder content in `text/`, `tables/`, and `figures/` is
  intentionally generic — replace it with your own research.
- Paragraph indentation is set to `2em` (Chinese convention) in `main.tex`.
  For no-indent + vertical spacing style, uncomment `parskip` in
  `A_PreambleSettings.tex` and remove the `\setlength{\parindent}{2em}` line.
- `newtxtext` sets `\defaultfontfeatures{Extension=.otf,...}` which can leak
  into xeCJK's deferred font loads on some systems; the template resets it
  with `\defaultfontfeatures{}` right after loading (see
  `A_PreambleSettings.tex`).
- `main.pdf` in the repository is a compiled preview of the template.

## License

MIT — see [LICENSE](LICENSE). Feel free to use, modify, and redistribute.

---

### 中文说明

本模板由实际论文项目脱敏整理而来，保留了完整的工程结构（分节文件、表格、
TikZ 图形、参考文献），去除了所有研究内容与个人信息，可直接作为新论文的
起点。编译方式见上文；所有占位内容均标注了 "Placeholder / 占位" 提示，
请替换为你自己的内容。

