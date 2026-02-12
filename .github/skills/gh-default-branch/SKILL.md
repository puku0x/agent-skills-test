---
name: gh-default-branch
description: 'Retrieve the default branch name of the current Git repository using GitHub CLI. Use this skill when the user asks "What is the default branch?", "Get the default branch", "What is the main branch?", "Show me the base branch", or when other git operations require knowing the default branch name (e.g., for creating pull requests, comparing branches, or checking out the base branch).'
---

# Get Default Branch

## Overview

This skill retrieves the default branch name of the current Git repository using the GitHub CLI command `gh repo view --json defaultBranchRef --jq .defaultBranchRef.name`.

## When to Use

Use this skill when:

- The user requests the default branch name of the repository.
- Performing git operations that require knowledge of the default branch (e.g., creating pull requests, comparing branches, checking out the base branch).

## Usage

To get the default branch name, run the command:

```bash
gh repo view --json defaultBranchRef --jq .defaultBranchRef.name
```

The command will output the default branch name (e.g., `main`, `master`, `develop`).
