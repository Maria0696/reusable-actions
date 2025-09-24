# Lint Actions

![Lint Actions](https://img.shields.io/badge/lint-✅-green?style=flat-square)

## 📄 Description

This action checks the quality of all your GitHub Actions in the repository by validating the `action.yml` files using [`actionlint`](https://github.com/rhysd/actionlint).  
Perfect for keeping your actions **reusable, consistent, and error-free**.

---

## ⚙️ Inputs

| Input | Description | Required | Default |
|-------|------------|-----------|---------|
| `path` | Path to the folder containing your actions | No | `./actions` |

---

## 📝 Outputs

| Output | Description |
|--------|-------------|
| `result` | Linting result (`success` or `failure`) |

---

## 🚀 Example Usage

```yaml
name: Lint GitHub Actions

on:
  push:
    branches: ["main"]
  pull_request:
    branches: ["main"]

jobs:
  lint-actions:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: ./actions/lint-actions
        with:
          path: "./actions"
