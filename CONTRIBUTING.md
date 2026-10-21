# Contributing to visualmark-studio 🤝

First off, thank you for considering contributing to **visualmark-studio**! 🎉

Every contribution—whether it is a bug report, feature enhancement, code optimization, or documentation patch—is deeply valued.

<p align="left">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge" alt="PRs Welcome" />
  <img src="https://img.shields.io/badge/Conventional-Commits-FE5196?style=for-the-badge&logo=conventionalcommits&logoColor=white" alt="Conventional Commits" />
</p>

---

## 📜 Code of Conduct

> [!NOTE]
> By participating in this project, you agree to uphold an inclusive, respectful, and harassment-free environment for all contributors, maintainers, and community members.

---

## 🐛 Bug Reports & Feature Proposals

### 1. Reporting Bugs
- Search existing GitHub issues to verify the bug has not already been tracked.
- If unfiled, open a new **Bug Report** with:
  - Clear steps to reproduce the defect.
  - Expected behavior vs. actual outcome.
  - Runtime environment details (Node version, Python version, OS).
  - Terminal console error traces or screenshots.

### 2. Proposing Features
- Open an **Enhancement Proposal** issue to discuss the motivation and design before starting work.
- Outline user benefits, edge cases, and proposed architectural approach.

---

## 📝 Conventional Commits Specification

We adhere to the [Conventional Commits](https://www.conventionalcommits.org/) specification for automated semantic versioning:

| Type | Badge | Description |
| :--- | :--- | :--- |
| `feat` | ![Feat](https://img.shields.io/badge/-Feature-007ACC?style=flat-square) | A new user-facing capability |
| `fix` | ![Fix](https://img.shields.io/badge/-Fix-E05D44?style=flat-square)` | A bug fix or critical patch |
| `docs` | `![Docs](https://img.shields.io/badge/-Docs-4C1?style=flat-square) | Documentation adjustments only |
| `style` | ![Style](https://img.shields.io/badge/-Style-FFB13B?style=flat-square)| Formatting or whitespace adjustments |
| `refactor` | ![Refactor](https://img.shields.io/badge/-Refactor-9B59B6?style=flat-square)| Code restructuring without behavior change |
| `perf` | ![Perf](https://img.shields.io/badge/-Performance-FF8000?style=flat-square) | Optimization that improves runtime throughput |
| `test` | ![Test](https://img.shields.io/badge/-Test-00C7B7?style=flat-square) | Adding or correcting automated tests |
| `chore` | ![Chore](https://img.shields.io/badge/-Chore-7F8C8D?style=flat-square) | Build tooling, dependency, or config updates |

---

## 🚀 Git Branching & Pull Request Workflow

Follow this standard developer workflow using the terminal frame below:

```bash
# [zsh — 80×24]
# 1. Fork repository and checkout dedicated feature branch
$ git checkout -b feat/my-awesome-feature

# 2. Make atomic changes, run test suites, and commit
$ git add .
$ git commit -m "feat(core): implement high-throughput asynchronous pipeline"

# 3. Rebase onto latest upstream main and push branch
$ git fetch origin
$ git rebase origin/main
$ git push origin feat/my-awesome-feature
```

> [!IMPORTANT]
> Ensure all local test suites and linters pass with zero warnings before requesting review:
> ```bash
> npm test        # Frontend test suite
> pytest -v       # Backend test suite
> ```

Thank you for helping make **visualmark-studio** extraordinary! ❤️
