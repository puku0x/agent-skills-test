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

## PR format

The PR title follows this format:

```
<type>[optional scope]: <description>
```

- `<type>` and `[optional scope]` follow the same format as commit messages
- `<description>` must be written in Japanese
- `<description>` must end with a noun

## PR Description Template

The PR description should be written in Japanese and follow this template:

```markdown
## 概要

<!-- （修正の内容など） -->

- [ ] 変更内容1
- [ ] 変更内容2
- [ ] 不具合修正の内容

## 備考

<!-- （関連Issueなど） -->

- #123
```

## Workflow

### Step 1: Push to remote

Push the current branch to the remote repository:

```bash
git status
```

```bash
git push -u origin <branch-name>
```

### Step 2: Create a pull request

Create a pull request using the GitHub CLI:

```bash
gh pr create --title "<PR title>" --body "<PR description>"
```

Example:

```bash
gh pr create --title "chore: Prettier設定ファイルの追加" --body "## 概要

Prettierの設定ファイルを追加しました。

### 変更内容

- [x] \`.prettierignore\` の追加
- [x] \`.prettierrc\` の追加

## 備考

- #123"
```

- Enclose file names with extension (i.e., `*.md` `*.json` ) in the `<description>` field with backticks.
- Backticks must be escaped in the command line to avoid shell interpretation issues. **Important**

## References

- [Pull Request Template](../../PULL_REQUEST_TEMPLATE.md)
- [Pull Request Description Instructions](./references/pull-request-description.instructions.md)
