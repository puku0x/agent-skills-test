---
name: git-commit
description: This skill should be used when creating Git commit messages that follow Conventional Commits format. Use this skill after code changes are completed and before committing to the repository. The skill provides project-specific commit message conventions, type selection rules, scope determination based on directory structure, and quality checks to ensure commits follow the project's standards.
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
