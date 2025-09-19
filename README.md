# 🚀 reusable-actions

[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI/CD-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)](https://github.com/Maria0696/reusable-actions/actions)
[![License](https://img.shields.io/badge/License-MIT-2bbc8a?style=for-the-badge&logo=github&logoColor=white)](LICENSE)
[![GitHub Stars](https://img.shields.io/badge/Stars-0-F7DF1E?style=for-the-badge&logo=github&logoColor=black)](https://github.com/Maria0696/reusable-actions/stargazers)

---

## 🌟 Overview

**`reusable-actions`** is your **ultimate toolkit of reusable GitHub Actions**. Automate workflows, CI/CD, testing, and deployments across multiple repositories with minimal setup.

> “Write once, reuse everywhere.” ⚡

---

## 📦 Actions Included

| Action        | Badge                                                                 | Description                        | Inputs                                   |
|---------------|-----------------------------------------------------------------------|------------------------------------|------------------------------------------|
| `lint`        | ![Lint](https://img.shields.io/badge/lint-✅-green?style=flat-square) | Runs linter & auto-fixes code      | `path` (string), `fix` (boolean)         |
| `test`        | ![Test](https://img.shields.io/badge/test-✅-blue?style=flat-square)  | Runs unit/integration tests        | `path` (string)                          |
| `deploy`      | ![Deploy](https://img.shields.io/badge/deploy-🚀-orange?style=flat-square) | Deploys to staging/production      | `environment` (string), `branch` (string)|
| `update-docs` | ![Docs](https://img.shields.io/badge/docs-📄-purple?style=flat-square) | Generates/updates documentation    | `output-path` (string)                   |

> More actions coming soon! 🔥

---

## ⚡ Quick Start

**1️⃣ Reference an action:**

```yaml
jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: your-username/reusable-actions/lint@v1
        with:
          path: "src/"
```

**2️⃣ Customize inputs:**

```yaml
with:
  path: "src/"
  fix: true
```

---

## 🖼 Workflow Visualization

```text
Push to main branch
        │
        ▼
   [Checkout code]
        │
        ▼
   [Lint & Format] ✅
        │
        ▼
     [Run Tests] 🧪
        │
        ▼
   [Deploy to Env] 🚀
        │
        ▼
   [Update Docs] 📄
```

---

## 📌 Example: Full CI/CD Workflow

```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Run Linter
        uses: your-username/reusable-actions/lint@v1
        with:
          path: "src/"
          fix: true

      - name: Run Tests
        uses: your-username/reusable-actions/test@v1
        with:
          path: "tests/"

      - name: Deploy
        uses: your-username/reusable-actions/deploy@v1
        with:
          environment: "staging"
          branch: "main"

      - name: Update Docs
        uses: your-username/reusable-actions/update-docs@v1
        with:
          output-path: "docs/"
```

---

## 🌈 Contributing

We ❤️ contributions!

1. Fork the repository
2. Create your feature branch: `git checkout -b feature/my-action`
3. Commit your changes: `git commit -m "Add new action"`
4. Push to your branch: `git push origin feature/my-action`
5. Open a Pull Request

---

## 📜 License

MIT License. See [LICENSE](LICENSE) for details.

---

> Made with ❤️ & ☕ by developers, for developers.