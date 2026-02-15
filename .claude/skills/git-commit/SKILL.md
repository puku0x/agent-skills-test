---
name: git-commit
description: Create Git commit messages following Conventional Commits format with automatic type and scope detection. Use when asked to "commit changes", "create a commit", "write commit message", or when ready to commit staged code. Supports feat, fix, docs, refactor, test, build, ci, chore, and revert types with project-specific scope determination based on file paths and directory structure.
---

# Git Commit Skill

This skill guides the creation of Git commit messages that follow the Conventional Commits format with project-specific conventions.

Read @.github/skills/git-commit/SKILL.md

## Notes

- Commit messages must be written in English.
- If there are staged changes, determine the commit message based only on the staged changes.
- The commit message must clearly state that the pull request was created by Claude Code.

```
feat(utils): update xxx function

🤖 Generated with [Claude Code](https://claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>
```
