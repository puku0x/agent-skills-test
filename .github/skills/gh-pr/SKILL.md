---
name: gh-pr
description: Create pull requests with proper title format, description template and project conventions. Use when asked to "create a PR", "create pull request", "open a PR", "submit PR", or when ready to push changes and open PR for review. Automatically formats PR titles with type and scope (feat, fix, docs, etc.), generates description template in Japanese, and uses gh CLI for PR creation.
user-invocable: false
---

# GitHub Pull Request Creation Skill

This skill guides the creation of GitHub pull requests following project-specific conventions.

## When to Use

Use this skill when:

- Ready to create a pull request for review
- Need to push branch to remote and open PR

## Instructions

### Step 1: Push to remote

Push the current branch to the remote repository:

```bash
git push -u origin $(git rev-parse --abbrev-ref HEAD)
```

### Step 2: Create a pull request

Create a pull request using the GitHub CLI:

```bash
gh pr create --title "<PR title>" --body "<PR description>"
```

#### Format of PR title

The PR title follows this format:

```
<type>[optional scope]: <description>
```

- `<type>` and `[optional scope]` follow the same format as commit messages
- `<description>` must be written in Japanese
- `<description>` must end with a noun

#### Format of PR description

The PR description should be written in Japanese and follow this template:

```markdown
## 概要

<!-- （修正の内容など） -->

- [ ] 変更内容 1
- [ ] 変更内容 2
- [ ] 不具合修正の内容

## 備考

<!-- （関連Issueなど） -->

- #123
```

#### Example

```bash
gh pr create --title "docs(github): カスタムインストラクションの追加" --body "## 概要

GitHub Copilot 用のカスタムインストラクションを追加しました。

### 変更内容

- [x] `.github/custom-instructions.md` の追加
- [x] `.github/instructions/*.md` の追加

## 備考

- #123"
```

## Notes

- **Important** The `type` and `scope` in the PR title must be written in English while the `description` must be written in Japanese. (e.g., `feat(frontend): 〜の追加`)
- Enclose file names with extension (i.e., `*.md` `*.json` ) in the `<description>` field with backticks.
  - Backticks must be escaped in the command line to avoid shell interpretation issues on GitHub Copilot.

## References

- [Pull Request Template](../../PULL_REQUEST_TEMPLATE.md)
- [Pull Request Description Instructions](./references/pull-request-description.instructions.md)
