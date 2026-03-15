```{image} https://www.vectorlogo.zone/logos/python/python-icon.svg
:height: 60px
:align: left
```

# Python

```{admonition} Quick Facts
:class: tip
- **Typing:** Dynamic
- **Paradigm:** Multi-paradigm (OOP, functional, procedural)
- **Use cases:** Data science, ML, scripting, web backends, automation
- **Version:** Use 3.11 for ML related projects
```
::::{grid} 2 2 3 3

:::{grid-item-card}
:link: ../frameworks/uv
:link-type: doc

```{image} https://plugins.jetbrains.com/files/24963/635594/icon/default.svg
:height: 25px
:align: left
```
**uv**

Python package manager.
:::
::::

---

::::{dropdown} 📦 Installation

**Mac OS**
```bash
brew install python
```

**Linux**
```bash
sudo apt update
sudo apt install python3
```

::::

:::{dropdown} ⚡ Hello World

```python
print("Hello World!)
```

:::

:::{dropdown} 🔤 Data Types & Variables

**Core types**
```python
x = 69          # int
y = 3.14        # float
name = "Ada"    # str
flag = True     # bool
nothing = None  # NoneType
```

**Collections**
```python
nums = [1, 2, 3]                # list (mutable)
coords = (10, 20)               # tuple (immutable)
unique = {1, 2, 3}              # set (unique items)
user = {"name": "Ada", "id": 1} # dict (key/value)
```

**Type checks and casting**
```python
isinstance(x, int)
int("7")
float("3.5")
str(123)
```

:::

::::{dropdown} 🧩 Functions

:::{dropdown} OpenAI
Content for OpenAI
:::

:::{dropdown} Claude
Content for Claude
:::

::::

:::::{dropdown} 📚 Essential Packages

::::{dropdown} Dot-Env

:::{dropdown} Installation
```bash
pip install python-dotenv
```
```bash
uv add python-dotenv
```
:::

:::{dropdown} Initialization
```python
from dotenv import load_dotenv

load_dotenv()
```

```python
import os

api_key = os.getenv("API_KEY")
```
:::

::::
:::::
