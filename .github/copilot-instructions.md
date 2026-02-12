# Custom instructions for Copilot

## General

- Always respond in Japanese using JLPT N1 level vocabulary and grammar.
- Always use the framework of phrase structure grammar, compose sentences that are easy to understand.

## Code Review

The following instructions are only to be applied when performing a code review.

### General code review guide

- [ ] Always provide a critical review of the code changes.
- [ ] Always provide feedback in a constructive and respectful manner.
- [ ] Ensure that the code adheres to the project's coding standards and best practices.
- [ ] Check for potential bugs or issues in the code.
- [ ] Suggest improvements or optimizations where applicable.
- [ ] Verify that the code is well-documented and easy to understand.
- [ ] Ensure that the code is tested and that tests are comprehensive.
- [ ] Provide specific examples or references to support your feedback.

### Prompt Files review guide

**Only apply to files `.github/prompt/*.prompt.md`**

- [ ] The prompt has markdown front matter.
- [ ] The prompt has a `mode` field specified of either `agent` or `ask`.
- [ ] The prompt has a `description` field.
- [ ] The `description` field is not empty.
- [ ] The `description` field value is wrapped in single quotes.
- [ ] The file name is lower case, with words separated by hyphens.
- [ ] Encourage the use of `tools`, but it's not required.
- [ ] Strongly encourage the use of `model` to specify the model that the prompt is optimized for.

### Custom Instructions review guide

**Only apply to files `.github/instructions/*.instructions.md`**

- [ ] The instruction has markdown front matter.
- [ ] The instruction has a `description` field.
- [ ] The `description` field is not empty.
- [ ] The `description` field value is wrapped in single quotes.
- [ ] The file name is lower case, with words separated by hyphens.
- [ ] The instruction has an `applyTo` field that specifies the file or files to which the instructions apply. If they wish to specify multiple file paths they should formatted like `'**.js, **.ts'`.

### Custom Agents review guide

**Only apply to files `.github/agents/*.agent.md`**

- [ ] The chat mode has markdown front matter.
- [ ] The chat mode has a `description` field.
- [ ] The `description` field is not empty.
- [ ] The `description` field value is wrapped in single quotes.
- [ ] The file name is lower case, with words separated by hyphens.
- [ ] Encourage the use of `tools`, but it's not required.
- [ ] Strongly encourage the use of `model` to specify the model that the chat mode is optimized for.

## Agent Skills review guide

**Only apply to folders in the `.github/skills/` directory**

- [ ] The skill folder contains a `SKILL.md` file.
- [ ] The SKILL.md has markdown front matter.
- [ ] The SKILL.md has a `name` field.
- [ ] The `name` field value is lowercase with words separated by hyphens.
- [ ] The `name` field matches the folder name.
- [ ] The SKILL.md has a `description` field.
- [ ] The `description` field is not empty, at least 10 characters, and maximum 1024 characters.
- [ ] The `description` field value is wrapped in single quotes.
- [ ] The folder name is lower case, with words separated by hyphens.
- [ ] Any bundled assets (scripts, templates, data files) are referenced in the SKILL.md instructions.
- [ ] Bundled assets are reasonably sized (under 5MB per file).

### Security guide

- [ ] NEVER commit confidential files.
- [ ] NEVER store secret information, use environment variables.
- [ ] NEVER include authentication information in logs or outputs.

### Terminology guide

Terminology should be consistent and used without abbreviation.

- [ ] The term "GitHub" is case-sensitive.
- [ ] The word "Custom instructions" is expressed as "カスタムインストラクション" in Japanese.

## Pull Request

The following instructions are only to be applied when creating a pull request.

- [ ] Always refer [`.github/PULL_REQUEST_TEMPLATE.md`](PULL_REQUEST_TEMPLATE.md) as a template for your pull requests.
- [ ] Ensure that the pull request template is followed correctly.

## Agent Skills

The following agent skills are available in `.github/skills/*`.

- `/gh-default-branch` - The skill to retrieve the default branch name of the current Git repository
- `/gh-pr` - The skill to create GitHub pull requests with proper formatting
- `/git-branch` - The skill to create Git branches with proper naming conventions
- `/git-commit` - The skill to create Git commits with proper naming conventions
