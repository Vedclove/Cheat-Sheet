---
title: Welcome to Ved's Cheat-Sheet
description: A personal, living reference book for programming, data science, and developer tools — built with Jupyter Book and MyST Markdown.
author: Vishal Lavangare (Vedclove)
keywords: cheat-sheet, reference, myst, jupyter-book, programming
---

# Ved's Cheat-Sheet

```{epigraph}
The best way to remember something is to write it down — and the best way to share it is to build a book.

-- Vishal Lavangare
```

Welcome to **Ved's Cheat-Sheet** — a living, growing personal knowledge base built with [Jupyter Book](https://jupyterbook.org) and {abbr}`MyST (Markedly Structured Text)` Markdown. This book serves as a quick-reference guide, covering everything from programming syntax to development workflows.

```{note}
This book is a **work in progress**. New pages and sections are added regularly.
Contributions and suggestions are always welcome via [GitHub Issues](https://github.com/Vedclove/Cheat-Sheet/issues).
```

% ---------------------------------------------------------
% TABLE OF CONTENTS (rendered as the book's TOC sidebar)
% ---------------------------------------------------------

```{tableofcontents}
```

---

## About This Project

```{admonition} What is a Cheat-Sheet?
:class: tip

A **cheat sheet** is a concise set of notes used for quick reference. Unlike tutorials or textbooks, it skips lengthy explanations and gets straight to the **syntax**, **commands**, and **patterns** you need — when you need them.
```

This project is authored by **Vishal Lavangare** (alias {sup}`Vedclove`) and is publicly hosted at [github.com/Vedclove/Cheat-Sheet](https://github.com/Vedclove/Cheat-Sheet).

The book is built using:

- [Jupyter Book](https://jupyterbook.org) — for beautiful, publication-quality books from Markdown and Notebooks
- [MyST Markdown](https://myst-parser.readthedocs.io) — a powerful Markdown flavor supporting roles and directives
- [GitHub Actions](https://github.com/features/actions) — for automated CI/CD builds and deployments
- [Sphinx](https://www.sphinx-doc.org) — the underlying Python documentation engine

---

## What's Inside

(chapters-overview)=
### Chapters at a Glance

```{list-table} Book Chapters Overview
:header-rows: 1
:name: chapters-table
:widths: 25 50 25

* - Chapter
  - Description
  - Format
* - {doc}`markdown`
  - MyST Markdown syntax, roles, directives, and formatting tips
  - `.md`
* - {doc}`notebooks`
  - Working with Jupyter Notebooks as content pages with live code
  - `.ipynb`
* - {doc}`markdown-notebooks`
  - Combining Markdown prose with executable code cells
  - `.md` + code
```

---

## How to Navigate

```{tip}
Use the **sidebar** on the left to jump between chapters. Use {kbd}`Ctrl+K` (or {kbd}`⌘+K` on macOS) to open the search bar anywhere in the book.
```

**Step-by-step navigation guide:**

1. Browse chapters using the **Table of Contents** in the left sidebar
2. Use the **Previous / Next** buttons at the bottom of each page
3. Click the {kbd}`↑` / {kbd}`↓` arrow icons to navigate sections
4. Use the **download** buttons in the top bar to export any page as `.pdf` or `.ipynb`
5. Click **"Open in Colab"** or **"Launch Binder"** on notebook pages for interactive execution

---

## MyST Formatting Showcase

> This section is the **core reference** for MyST syntax. Each subsection demonstrates a specific feature — bookmark it for future use.

% ================================================================
% SECTION: ADMONITIONS
% ================================================================

(admonitions)=
### Admonitions (Callout Boxes)

Admonitions are styled callout boxes. Here are all the built-in types:

```{note}
**Note** — Neutral, supplementary information.
```

```{warning}
**Warning** — Something might break or go wrong if you ignore this.
```

```{important}
**Important** — Pay close attention to this.
```

```{tip}
**Tip** — A helpful hint or best practice.
```

```{caution}
**Caution** — Proceed with care; this is potentially risky.
```

```{danger}
**Danger** — This can cause serious, hard-to-reverse harm.
```

```{seealso}
**See Also** — Related pages: {doc}`markdown`, {doc}`notebooks`
```

```{hint}
**Hint** — A subtle nudge in the right direction.
```

```{error}
**Error** — This is what a documented error looks like.
```

Custom admonitions use `{admonition}` with a title and optional class:

```{admonition} Pro Tip: Use Keyboard Shortcuts
:class: tip

Press {kbd}`s` to focus the **search bar** instantly. Press {kbd}`t` to open the **table of contents** panel.
```

% ================================================================
% SECTION: CODE BLOCKS
% ================================================================

(code-blocks)=
### Code Blocks

**Fenced code block** with syntax highlighting:

```python
# A simple Python example
def greet(name: str) -> str:
    return f"Hello, {name}!"

print(greet("World"))
```

**`{code-block}` directive** — supports line numbers, captions, and line emphasis:

```{code-block} python
:caption: Building this book from the terminal
:linenos:
:emphasize-lines: 3

pip install jupyter-book      # install the tool
cd /path/to/repo              # navigate to your project
jb build mybook/              # <- this builds the HTML book
```

**Bash example:**

```{code-block} bash
:caption: Common Jupyter Book Commands

# Build the book
jb build mybook/

# Clean the build cache
jb clean mybook/

# Create a new book scaffold
jb create my-new-book/
```

Inline code uses backticks: `python --version`, `git status`, `pip install`.

% ================================================================
% SECTION: MATH
% ================================================================

(math-section)=
### Math & Equations

Inline math uses single dollar signs: $f(x) = ax^2 + bx + c$

Block math (unnumbered) uses double dollar signs:

$$
\sum_{k=1}^{n} k = \frac{n(n+1)}{2}
$$

Named, referenceable equations use the `{math}` directive:

```{math}
:label: euler-identity
e^{i\pi} + 1 = 0
```

Cross-reference it with: Equation {eq}`euler-identity` is Euler's Identity — often called the most beautiful equation in mathematics.

Another named equation:

```{math}
:label: gaussian
\int_{-\infty}^{\infty} e^{-x^2}\, dx = \sqrt{\pi}
```

The Gaussian integral {eq}`gaussian` appears frequently in probability and statistics.

% ================================================================
% SECTION: TABLES
% ================================================================

(tables-section)=
### Tables

**Standard Markdown table:**

| Syntax | Description | Example |
|:-------|:-----------:|--------:|
| `**text**` | Bold | **bold** |
| `*text*` | Italic | *italic* |
| `` `code` `` | Inline code | `code` |
| `~~text~~` | Strikethrough | ~~strike~~ |
| `[text](url)` | Hyperlink | [link](https://example.com) |

**`{list-table}` directive** — great for wide tables or programmatic content:

```{list-table} MyST Roles Quick Reference
:header-rows: 1
:name: roles-table

* - Role
  - Syntax
  - Use Case
* - Subscript
  - `{sub}\`text\``
  - Chemical formulas: H{sub}`2`O
* - Superscript
  - `{sup}\`text\``
  - Exponents: E=mc{sup}`2`
* - Abbreviation
  - `{abbr}\`X (Long Form)\``
  - {abbr}`API (Application Programming Interface)`
* - Keyboard key
  - `{kbd}\`Key\``
  - {kbd}`Ctrl+C`, {kbd}`⌘+Z`
* - Document link
  - `{doc}\`page\``
  - {doc}`markdown`
* - Label reference
  - `{ref}\`label\``
  - {ref}`admonitions`
* - Equation ref
  - `{eq}\`label\``
  - {eq}`euler-identity`
* - Figure ref
  - `{numref}\`fig-label\``
  - {numref}`jb-logo`
```

% ================================================================
% SECTION: FIGURES
% ================================================================

(figures-section)=
### Figures

```{figure} https://jupyterbook.org/_static/logo-wide.svg
:name: jb-logo
:width: 320px
:align: center

**Figure 1** — The Jupyter Book logo. This book is built on top of it.
```

Cross-reference figures like this: see {numref}`jb-logo` for the Jupyter Book logo.

% ================================================================
% SECTION: DROPDOWNS
% ================================================================

### Dropdowns

```{dropdown} Click to reveal: Why use a Cheat-Sheet book?

A structured cheat-sheet **book** (vs. a single file) lets you:

1. Organize references by topic with a navigable sidebar
2. Include runnable Jupyter Notebook examples inline
3. Export to PDF, HTML, or share as a website
4. Version-control your knowledge with Git
5. Search across all pages instantly

```

```{dropdown} See: Git Quick Reference
:open:

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new repo |
| `git add .` | Stage all changes |
| `git commit -m "msg"` | Commit staged changes |
| `git push origin main` | Push to remote |
| `git log --oneline` | Compact commit history |

```

% ================================================================
% SECTION: TARGET LABELS & CROSS-REFS
% ================================================================

(cross-refs)=
### Cross-References & Labels

You can label any heading or block with `(label)=` placed above it, then reference it using `{ref}`:

- {ref}`admonitions` — jumps to the Admonitions section
- {ref}`code-blocks` — jumps to Code Blocks
- {ref}`math-section` — jumps to Math & Equations
- {ref}`tables-section` — jumps to Tables
- {ref}`cross-refs` — jumps to this very section

% ================================================================
% SECTION: DEFINITION LISTS
% ================================================================

### Definition Lists

Jupyter Book
: A tool for building beautiful, publication-quality books from Markdown and Jupyter Notebooks.

MyST Markdown
: {abbr}`MyST (Markedly Structured Text)` — a rich Markdown dialect supporting Sphinx roles and directives.

Sphinx
: The Python-based documentation engine that powers Jupyter Book under the hood.

Directive
: A multi-line content block that acts like a function, e.g., ` ```{note} ... ``` `.

Role
: An inline markup element that acts like a function, e.g., `` {kbd}`Ctrl` ``.

% ================================================================
% SECTION: FOOTNOTES
% ================================================================

### Footnotes

This sentence references a footnote.[^fn1]

Footnotes can contain any Markdown — links, **bold**, `code`, etc.[^fn2]

[^fn1]: Footnotes are defined anywhere in the document and automatically rendered at the bottom of the page.
[^fn2]: This is the second footnote. It contains `inline code` and a [link](https://jupyterbook.org).

% ================================================================
% SECTION: LINE BLOCKS
% ================================================================

### Line Blocks

Line blocks preserve newlines and indentation — useful for addresses, poetry, or structured prose:

| Vishal Lavangare
| GitHub: github.com/Vedclove
| Project: Cheat-Sheet
|     Branch: main

% ================================================================
% SECTION: MARGIN NOTES
% ================================================================

### Margin Notes

```{margin} Quick Tip
Margin notes appear in the right gutter and are ideal for side comments, links, or quick callouts without interrupting the main flow.
```

Margin content is placed using the `{margin}` directive. It renders alongside the main text in the page margin.

% ================================================================
% SECTION: EPIGRAPH & PULL-QUOTE
% ================================================================

### Epigraph & Pull-Quote

```{epigraph}
Programs must be written for people to read, and only incidentally for machines to execute.

-- Harold Abelson, *Structure and Interpretation of Computer Programs*
```

```{pull-quote}
Keep it simple. Keep it readable. Keep it in version control.
```

% ================================================================
% SECTION: SIDEBAR
% ================================================================

### Sidebar

```{sidebar} About the Author

**Vishal Lavangare** (Vedclove) is a developer who built this reference book as a personal productivity tool.

- GitHub: [Vedclove](https://github.com/Vedclove)
- Repo: [Cheat-Sheet](https://github.com/Vedclove/Cheat-Sheet)
```

The `{sidebar}` directive floats content to the side, letting it coexist with surrounding body text. It's great for short bios, glossary terms, or quick links.

% ================================================================
% SECTION: RUBRIC
% ================================================================

### Rubric (Un-numbered Heading)

```{rubric} This is a rubric
```

A `{rubric}` creates a styled, un-numbered heading — useful for visual separation without affecting the TOC hierarchy.

% ================================================================
% SECTION: COMMENTS
% ================================================================

### Comments

% This is a MyST comment — it will NOT appear in the rendered HTML output.
% Comments are useful for leaving developer notes in source files.

Comments in MyST use a `%` prefix. They are stripped from output entirely.

**Syntax:**
```
% This is a comment
% It won't appear in the rendered output
```

---

## Quick Reference Card

This is your at-a-glance cheat sheet for the cheat sheet:

```{list-table} MyST Formatting Quick Reference
:header-rows: 1
:stub-columns: 1

* - Feature
  - Directive / Syntax
  - Notes
* - Note box
  - ` ```{note} ``` `
  - Also: warning, tip, important, caution, danger, hint, seealso, error
* - Custom admonition
  - ` ```{admonition} Title ``` `
  - Use `:class: tip` etc. to style it
* - Code block
  - ` ```{code-block} python ``` `
  - Options: linenos, emphasize-lines, caption
* - Inline code
  - `` `code` ``
  - Standard Markdown
* - Math (inline)
  - `$formula$`
  - LaTeX syntax
* - Math (block)
  - `$$formula$$` or ` ```{math} ``` `
  - Use `:label:` for numbered equations
* - Figure
  - ` ```{figure} path ``` `
  - Use `:name:` to make cross-referenceable
* - Dropdown
  - ` ```{dropdown} Title ``` `
  - Use `:open:` to start expanded
* - Table (list-table)
  - ` ```{list-table} ``` `
  - Use `:header-rows: 1`
* - Target label
  - `(label)=` above heading
  - Reference with `{ref}\`label\``
* - Cross-reference
  - `{doc}\`page\``, `{ref}\`label\``, `{eq}\`label\``
  - Links to pages, headings, equations
* - Figure ref
  - `{numref}\`fig-name\``
  - Auto-numbered "Figure X"
* - Abbreviation
  - `{abbr}\`X (Full Form)\``
  - Shows tooltip on hover
* - Keyboard
  - `{kbd}\`Key\``
  - Renders as a styled key badge
* - Sub/Superscript
  - `{sub}\`x\``, `{sup}\`x\``
  - Inline sub/superscript
* - Footnote
  - `[^label]` + `[^label]: text`
  - Renders at page bottom
* - Definition list
  - `Term\n: Definition`
  - CommonMark extension
* - Line block
  - `\| line one\n\| line two`
  - Preserves line breaks
* - Margin note
  - ` ```{margin} ``` `
  - Floats to right gutter
* - Epigraph
  - ` ```{epigraph} ``` `
  - Styled block quote with attribution
* - Pull-quote
  - ` ```{pull-quote} ``` `
  - Highlighted inline quote
* - Sidebar
  - ` ```{sidebar} Title ``` `
  - Floated side content block
* - Rubric
  - ` ```{rubric} Title ``` `
  - Un-numbered styled heading
* - Comment
  - `% comment text`
  - Invisible in output
* - TOC
  - ` ```{tableofcontents} ``` `
  - Renders the book's TOC tree
* - Bibliography
  - ` ```{bibliography} ``` ` + `{cite}\`key\``
  - Requires a `.bib` file
```

---

## Contributing

Spotted a mistake or want to add a new topic?

1. Fork the repo at [github.com/Vedclove/Cheat-Sheet](https://github.com/Vedclove/Cheat-Sheet)
2. Create a new branch: `git checkout -b add/my-topic`
3. Add or edit `.md` / `.ipynb` files in the `mybook/` directory
4. Update [`_toc.yml`](https://github.com/Vedclove/Cheat-Sheet/blob/main/mybook/_toc.yml) to include your new page
5. Submit a Pull Request

```{important}
Please keep each cheat-sheet page **concise and scannable**. Prefer tables, code blocks, and bullet lists over long prose paragraphs.
```

---

*Built with [Jupyter Book](https://jupyterbook.org) · Authored by [Vedclove](https://github.com/Vedclove) · Source on [GitHub](https://github.com/Vedclove/Cheat-Sheet)*
