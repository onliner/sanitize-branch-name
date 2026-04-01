# 🌿 Sanitize Branch Name

A lightweight GitHub Action that determines the current branch name  
and generates a sanitized version safe for artifact names, cache keys, and file paths.

[![GitHub Actions][github-actions-badge]][github-actions-link]
[![Shell][shell-badge]][shell-link]
[![License][license-badge]][license-link]

---

## ✨ Features

- Detects the current branch name automatically
- Supports both `push` and `pull_request` workflows
- Replaces `/` and `_` with `-`
- Exposes both original and sanitized branch names as outputs
- Lightweight and dependency-free

---

## 📦 Outputs

| Output                  | Description                                  |
|-------------------------|----------------------------------------------|
| `branch_name`           | Original branch name                         |
| `sanitized_branch_name` | Branch name with `/` and `_` replaced by `-` |

---

## 🚀 Usage

```yaml
- name: Sanitize branch name
  id: branch
  uses: onliner/sanitize-branch-name@v1

- name: Print outputs
  run: |
    echo "Original: ${{ steps.branch.outputs.branch_name }}"
    echo "Sanitized: ${{ steps.branch.outputs.sanitized_branch_name }}"
```

---

## 🧪 Example

| Branch name         | Sanitized branch name |
|---------------------|-----------------------|
| `feature/login-ui`  | `feature-login-ui`    |
| `hotfix_bug_123`    | `hotfix-bug-123`      |
| `release/v1_2_0`    | `release-v1-2-0`      |

---

## 💡 Use Cases

- Artifact naming (upload-artifact)
- Cache keys (actions/cache)
- Docker tags
- File paths
- Any CI workflow where branch names must be filesystem-safe

---

## 📜 License

Released under the [MIT License](LICENSE).

[github-actions-badge]: https://img.shields.io/badge/github%20actions-composite-blue
[github-actions-link]: https://docs.github.com/en/actions
[shell-badge]: https://img.shields.io/badge/shell-bash-black
[shell-link]: https://www.gnu.org/software/bash/
[license-badge]: https://img.shields.io/badge/license-MIT-green
[license-link]: LICENSE
