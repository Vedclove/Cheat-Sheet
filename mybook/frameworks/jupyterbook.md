```{image} https://jupyterbook.org/_static/logo-wide.svg
:height: 60px
:align: left
```

# JupyterBook

```{admonition} Quick Facts
:class: tip
- **Type:** Documentation & book builder
- **Use cases:** Technical books, docs sites, cheat-sheets, course notes, research reports
- **Key concepts:** `_config.yml`, `_toc.yml`, MyST Markdown, Sphinx, Directives, Roles
- **CLI tool:** `jb` (jupyter-book)
- **Version:** 0.x (Sphinx-based) — pin `jupyter-book<2`
```

---

:::{dropdown} 📦 Installation & Setup
:open:

**Install**
```bash
pip install "jupyter-book<2"
```

**Create a new book**
```bash
jb create mybook
```

**Build**
```bash
jb build mybook
```
:::

:::{dropdown} 📁 Project Structure

```text
mybook/
  _config.yml
  _toc.yml
  intro.md
  chapter-1/
    index.md
```
:::

:::{dropdown} 📝 Content Types

**Markdown pages**
```text
intro.md
chapter-1/section.md
```

**Notebooks**
```text
notebooks/example.ipynb
```

**MyST directives**
````md
```{admonition} Title
:class: tip
Content
```
````
:::

:::{dropdown} 🔧 _config.yml Reference

```yaml
title: My Book
author: Your Name
logo: _static/logo.png
execute:
  execute_notebooks: auto
repository:
  url: https://github.com/user/repo
html:
  use_repository_button: true
```
:::

:::{dropdown} 🗂️ _toc.yml Reference

```yaml
format: jb-book
root: intro
chapters:
  - file: chapter-1/index
    sections:
      - file: chapter-1/section
```
:::

:::{dropdown} 🏗️ Building & Previewing

```bash
jb build mybook
jb build mybook --all
python -m http.server -d mybook/_build/html 8000
```
:::

:::{dropdown} 🚀 Deployment (GitHub Pages)

```bash
jb build mybook
ghp-import -n -p -f mybook/_build/html
```
:::
