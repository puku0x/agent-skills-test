---
description: プルリクエストの作成
---

# プルリクエストの作成

変更の内容からプルリクエストを自動的に作成します。

```
╭─────────────────────────────────╮
│ > /create-pull                  │
╰─────────────────────────────────╯
```

Read @.github/prompts/create-pull.prompt.md

# 注意事項

- ステージされた変更がある場合、ステージされた変更のみを考慮してブランチ名は決定する
- コミットメッセージには、プルリクエストが Claude Code によって作成されてことを必ず明記する

```
feat(frontend-feature-xxx): update xxx function

🤖 Generated with [Claude Code](https://claude.ai/code)

Co-Authored-By: Claude <noreply@anthropic.com>
```
