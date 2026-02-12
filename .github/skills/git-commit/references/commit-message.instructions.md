---
applyTo: '**'
description: 'Conventional Commits'
---

# コミットメッセージ

コミットメッセージは [Conventional Commits](https://www.conventionalcommits.org/ja/v1.0.0/) に従って記述する。

## フォーマット

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### type（必須）

- `feat`: 新機能や既存機能の変更
- `fix`: バグ修正
- `docs`: ドキュメントのみの変更
  - `*.md` を追加、変更した場合
- `refactor`: リファクタリング（バグ修正や機能追加を含まない変更）
- `perf`: パフォーマンス向上
- `test`: テスト追加・修正
  - `*.spec.*` `*.spec.*.snap` を追加、変更した場合
- `build`: ビルドシステムや外部依存に関する変更
- `ci`: CI 関連の変更
  - `.github/*` 内のファイルの修正が含まれる場合は優先して `ci` を選択する
- `chore`: その他の変更
  - `*.json` の修正
  - `*.config.mjs` `*.config.cjs` `*.config.js` `*.config.ts` の修正
  - `.gitignore` `.gitattributes` の修正
  - `.prettierignore` `.prettier` の修正
- `revert`: 以前のコミットの取り消し

### scope（任意）

影響範囲（例: `frontend-feature-*`, `frontend-shared`, `ui` など）を指定します。

Scope は変更されたファイルのあるディレクトリ名をもとに設定します。

- ディレクトリ名が `.gitignore` または `.gitattributes` の時は設定しない
- ディレクトリ名が `.prettierignore` または `.prettier` の時は設定しない
- ディレクトリ名が `README.md` の時は設定しない
- ディレクトリ名が `.claude/` または `.mcp.json` で始まる時 `claude`
- ディレクトリ名が `.github/` で始まる時 `github`
- ディレクトリ名が `.vscode/` で始まる時 `vscode`
- ディレクトリ名が `apps/frontend/` で始まる時 `frontend`
- ディレクトリ名が `apps/frontend-e2e/` で始まる時 `frontend-e2e`
- ディレクトリ名が `libs/frontend/environments/` で始まる時 `frontend-environments`
- ディレクトリ名が `libs/frontend/feature-xxx/` で始まる時 `frontend-feature-xxx`
- ディレクトリ名が `libs/frontend/shared/` で始まる時 `frontend-shared`
- ディレクトリ名が `libs/ui/` で始まる時 `ui`
- ディレクトリ名が `libs/workspace-plugin/` で始まる時 `workspace-plugin`

### description（必須）

変更内容を簡潔に記述してください（50 文字以内推奨）。

### body（任意）

変更理由や詳細を記載します。

### footer（任意）

BREAKING CHANGE や関連 Issue（例: `BREAKING CHANGE: ...`, `Closes #123`）を記載します。

破壊的変更の場合は `BREAKING CHANGE: 破壊的変更内容` を追加してください。

```
feat(frontend-feature-legacy): remove legacy page

BREAKING CHANGE: The legacy page is no longer available.
```

## コミットメッセージの例

### feat

```
feat(frontend): add user page
```

```
feat(frontend-environments): add `NEXT_PUBLIC_FEATURE_XXX`
```

```
feat(frontend): enable `NEXT_PUBLIC_FEATURE_XXX` on production
```

```
feat(frontend-feature-xxx): add social login
```

```
feat(frontend-shared): add shared layout
```

```
feat(ui): add button component
```

```
feat(workspace-plugin): add feature generator
```

### fix

```
fix(frontend): fix bug
```

```
fix(frontend-feature-xxx): fix validation
```

```
fix(frontend-shared): fix condition
```

```
fix(ui): fix style
```

#### docs

```
docs: update README.md
```

```
docs(github): update copilot-instructions.md
```

```
docs(github): refactor prompts
```

```
docs(claude): update commands
```

```
docs(frontend-feature-xxx): add README.md
```

### refactor

```
refactor(frontend): refactor layout.tsx
```

```
refactor(frontend-feature-xxx): refactor form logic
```

### test

```
test(frontend): add unit tests for login
```

```
test(frontend-feature-xxx): add tests for useSignInFacade
```

```
test(ui): update snapshots
```

### ci

```
ci(github): update ci.yml
```

```
ci(nx): enable nx agents
```

### chore

```
chore(deps): update dependencies
```

```
chore: refactor tsconfig.json
```

```
chore: update mise.toml
```

```
chore(frontend-feature-xxx): update project.json
```

```
chore(frontend): fix next.config.js
```
