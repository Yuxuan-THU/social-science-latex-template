# 社会科学论文 LaTeX 模板

一份干净、可复现的 **XeLaTeX** 论文模板，专为社会科学论文设计 ——
告别排版折磨，专注研究本身。

**英文为主、中文就绪。** Times 字体、期刊级三线表、TikZ 插图、
author–year 引用，开箱即用。

---

## ✨ 特性

- **专业排版** —— Times 字体（`newtxtext` / `newtxmath`）、1 英寸页边距、
  1.35 倍行距、标准 12pt 稿件格式
- **双语就绪** —— 通过 `xeCJK` 完整支持中文；英文为主，需要时随时插入
  中文段落（自动识别系统字体：Windows 用宋体/黑体，macOS/Linux 用 Noto CJK）
- **期刊级表格** —— `booktabs` + `threeparttable` + `makecell`，
  宽表自动缩放（`adjustbox`）
- **可复现插图** —— 每张图都是独立的 TikZ 源文件，编译即得 PDF，
  随时重新生成，告别手工改图
- **Harvard 引用** —— `natbib` + AEA 风格 `.bst`；所有文献集中在一个
  `references.bib`（UTF-8，支持中文文献）
- **按节组织** —— `text/` 下一节一文件；表格、图片各归其位；
  附录编号自动处理

## 🚀 快速开始

```bash
xelatex main.tex
bibtex  main
xelatex main.tex
xelatex main.tex
```

或使用 `latexmk`：

```bash
latexmk -xelatex main.tex
```

**Overleaf：** 上传 zip → 编译器选择 **XeLaTeX** → 完成。

> 仓库内附编译好的预览 [`main.pdf`](main.pdf)。

## 📁 项目结构

```
.
├── main.tex                 # 主文件：标题、章节、附录
├── A_PreambleSettings.tex   # 全局设置，一处修改全部生效
├── references.bib           # 参考文献（UTF-8，支持中文）
├── aeaown.bst               # Harvard（作者-年份）引用样式
├── text/                    # 正文分节，一节一文件
├── tables/                  # 表格文件
└── figures/                 # TikZ 源文件 + 编译后的 PDF（同名）
```

## ✏️ 快速定制

1. **标题与作者** —— 修改 `main.tex` 中的 `\title{...}` / `\author{...}`
2. **正文内容** —— 替换 `text/` 下的占位文件
3. **表格** —— 表格文件放入 `tables/`，在需要处 `\input`
4. **插图** —— 在 `figures/` 添加 `my-figure.tex`，编译为 `my-figure.pdf`，
   用 `\includegraphics{my-figure.pdf}` 插入
5. **字体** —— 在 `A_PreambleSettings.tex` 中切换中文字体

## 📄 开源协议

MIT —— 随意使用、修改、再分发。

---

*为想专注于研究、而非排版的你而做。*
