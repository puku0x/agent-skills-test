---
name: git-branch
description: Create Git branches with automatic type detection and project-specific naming conventions. Use when asked to "create a branch", "make a new branch", "create branch for changes", or when ready to organize code changes into a new branch. Supports feat, fix, docs, refactor, test, build, ci, chore, revert, and perf branch types with automatic type selection based on changed file patterns.
---

# Git Branch Skill

This skill guides the creation of Git branches with project-specific naming conventions.

## When to Use

Use this skill when:

- You have made changes to the codebase and need to create a new branch for those changes.
- You want to ensure that the branch name follows the project's naming conventions.

## Workflow

### Step 1: Check staged changes

Use the following command to view staged changes:

```bash
git diff --staged
```

If there are no staged changes, check unstaged changes with:

```bash
git diff
```

### Step 2: Determine branch type and description

The format for branch names is:

```
<type>-<description>
```

- If there are only staged changes, base the branch name on the staged changes.
- If there are only unstaged changes, base the branch name on the unstaged changes.
- If there are both staged and unstaged changes, base the branch name on the staged changes.

**type** is determined based on the patterns of the changed files:

- `feat-`: New features or changes to existing features
- `fix-`: Bug fixes
- `refactor-`: Refactoring (changes that do not add features or fix bugs)
- `test-`: Adding or modifying tests (e.g., changes to `*.spec.*` or `*.spec.*.snap` files)
- `docs-`: Documentation-only changes (e.g., changes to `*.md` files)
- `ci-`: CI-related changes (e.g., changes to files in `.github/workflows/*` or `.github/actions/*`)
- `chore-`: Other changes (e.g., changes to `*.json`, configuration files like `*.config.js`, `.gitignore`, etc.)
- `revert-`: Reverting previous commits
- `build-`: Changes related to the build system or external dependencies
- `perf-`: Performance improvements

**description** should concisely describe the changes made, using hyphens to separate words.

## Step 3: Create the branch

Use `git switch -c` to create and switch to the new branch.

Example:

```bash
git switch -c feat-user-authentication
```

## References

- [branch-name.md](./references/branch-name.md)
