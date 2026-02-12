---
name: git-commit
description: This skill should be used when creating Git commit messages that follow Conventional Commits format. Use this skill after code changes are completed and before committing to the repository. The skill provides project-specific commit message conventions, type selection rules, scope determination based on directory structure, and quality checks to ensure commits follow the project's standards.
---

# Git Commit Skill

This skill guides the creation of Git commit messages that follow the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) format.

## When to Use

Use this skill when:

- Code changes are completed and ready to be committed
- Need to create a commit message that adheres to project conventions

## Commit Message Format

The commit message must follow this format:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Workflow overview

1. Check the staged files using `git diff --staged --name-only`.
   Ask user to stage changes if there are no staged files.
2. Determine the appropriate commit type and scope based on the staged files.

**type** must be selected from the following options:

- `feat`: New feature or change to existing functionality
- `fix`: Bug fix
- `docs`: Documentation-only changes (e.g., changes to `*.md` files)
- `refactor`: Refactoring (code changes that neither fix a bug nor add a feature)
- `perf`: Performance improvements
- `test`: Adding or modifying tests (e.g., changes to `*.spec.*` or `*.spec.*.snap` files)
- `build`: Changes affecting the build system or external dependencies
- `ci`: Changes to CI configuration files (e.g., changes within `.github/actions` or `.github/workflows`)
- `chore`: Other changes (e.g., changes to `*.json`, `*.config.mjs`, `*.config.cjs`, `*.config.js`, `*.config.ts`, `.gitignore`, `.gitattributes`, `.prettierignore`, `.prettier`)
- `revert`: Reverting a previous commit

**scope** should be determined based on the directory structure of the staged files. For example:

- If staged files are in `.claude/` or `.mcp.json`, use `claude`
- If staged files are in `.github/`, use `github`
- If staged files are in `.vscode/`, use `vscode`
- If staged files are in `apps/frontend/`, use `frontend`
- If staged files are in the root directory, do not set a scope

3. Craft a concise and descriptive commit message in English that adheres to the Conventional Commits format.

Example:

```bash
git commit -m "$(cat <<'EOF'
feat(utils): update xxx function

- Add xxx logic in xxx function
- Implement unit tests for xxx function

Co-Authored-By: Copilot <175728472+Copilot@users.noreply.github.com>
EOF
)"
```

Never use `\n` in the commit message. Use actual new lines.

## Notes

- Commit messages must be written in English. **Important**
- If there are staged changes, determine the commit message based only on the staged changes.
- The commit message must clearly indicate that it was created with Copilot.

## References

- [Commit message](./references/commit-message.instructions.md)
