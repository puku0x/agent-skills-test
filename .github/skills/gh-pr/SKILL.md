---
name: 'gh-pr'
description: 'This skill should be used when creating a pull request in GitHub. Use this skill after committing changes to the repository. The skill provides proper PR title format, description template, and ensures the PR follows project conventions.'
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
- Enclose file names with extension (i.e., `README.md` `settings.json` ) in the `<description>` field with backticks (`).

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

- `cat` コマンドを使用して、複数行の PR 説明を渡すことができます。

## References

- [Pull Request Template](../../PULL_REQUEST_TEMPLATE.md)
- [Pull Request Description Instructions](./references/pull-request-description.instructions.md)
