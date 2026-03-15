```{image} https://www.vectorlogo.zone/logos/github/github-icon.svg
:height: 60px
:align: left
```

# GitHub

```{admonition} Quick Facts
:class: tip
- **Type:** Git hosting & collaboration platform
- **Use cases:** Version control, code review, CI/CD (Actions), project management, open source
- **Key concepts:** Repos, Branches, Pull Requests, Issues, Actions, Releases
- **CLI tool:** `gh` (GitHub CLI)
```

---

:::{dropdown} 📦 Installation & Setup
:open:

**Git install**
```bash
git --version
```

**GitHub CLI**
```bash
brew install gh
gh --version
```

**Authenticate**
```bash
gh auth login
gh auth status
```
:::

:::{dropdown} 🌿 Branching & Commits

```bash
git checkout -b feature/my-change
git status
git add .
git commit -m "Add feature"
git push -u origin feature/my-change
```
:::

:::{dropdown} 🔀 Pull Requests & Code Review

```bash
gh pr create --fill
gh pr list
gh pr view <number>
gh pr checkout <number>
```
:::

:::{dropdown} ⚙️ GitHub Actions (CI/CD)

**Trigger and watch**
```bash
gh workflow list
gh workflow run <workflow-file.yml>
gh run list
gh run view <run-id>
```

**Minimal workflow**
```yaml
name: CI
on:
  push:
    branches: [main]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20
      - run: npm ci
      - run: npm test
```
:::

:::{dropdown} 🖥️ GitHub CLI (gh)

```bash
gh repo create
gh repo view
gh repo clone owner/repo
gh issue list
gh issue create -t "Bug" -b "Steps to reproduce"
```
:::

:::{dropdown} 🔑 SSH & Authentication

```bash
ssh-keygen -t ed25519 -C "you@example.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
gh ssh-key add ~/.ssh/id_ed25519.pub
ssh -T git@github.com
```
:::
