```{image} https://docs.astral.sh/uv/assets/logo-letter.svg
:height: 60px
:align: left
```

# uv

```{admonition} Quick Facts
:class: tip
- **Type:** Python package & project manager
- **Use cases:** Installing packages, managing virtual envs, running scripts, building & publishing packages
- **Key concepts:** Virtual environments, `pyproject.toml`, lockfiles, Python version management
- **Built with:** Rust (by Astral) — 10–100x faster than `pip`
- **Replaces:** `pip`, `pip-tools`, `pipx`, `virtualenv`, `pyenv`, `poetry`
```

---

:::{dropdown} 📦 Installation
:open:

**Install**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
uv --version
```

**Update**
```bash
uv self update
```
:::

:::{dropdown} 🚀 Basic Commands

```bash
uv --help
uv init
uv add requests
uv remove requests
uv sync
uv run python -V
```
:::

:::{dropdown} 📁 Project Management

**Create a project**
```bash
uv init myapp
cd myapp
```

**Add dependencies**
```bash
uv add fastapi
uv add "requests>=2.31"
```

**Remove dependencies**
```bash
uv remove fastapi
```
:::

:::{dropdown} 🐍 Python Version Management

```bash
uv python list
uv python install 3.12
uv python pin 3.12
uv python use 3.12
```
:::

:::{dropdown} 📜 Scripts & Tools

**Run scripts**
```bash
uv run python app.py
uv run pytest
```

**Run tools without installing**
```bash
uvx ruff check .
uvx black .
```
:::

:::{dropdown} 🔒 Lockfiles & Reproducibility

```bash
uv lock
uv sync --frozen
uv export -o requirements.txt
```
:::
