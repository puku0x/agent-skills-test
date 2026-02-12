---
applyTo: '**'
description: 'Pull request title and description'
---

# プルリクエストのタイトルと説明

## プルリクエストのタイトル

プルリクエストのタイトルは以下のフォーマットに従う。

```
<type>[optional scope]: <description>
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

- 必ず日本語で記載する
- 変更内容を簡潔に記述する（50 文字以内推奨）

### 例

- `feat(frontend): ユーザー認証機能の実装`
- `fix(frontend-feature-sign-in): ログインバリデーションエラーの修正`
- `docs: API仕様書の更新`

## プルリクエストの説明

プルリクエストの説明は以下のフォーマットに従う.

```
## 概要
<!-- （修正の内容など） -->
-

## 備考
<!-- （関連Issueなど） -->
```

### 概要（必須）

プルリクエストの目的や内容を簡潔に記載します。

### 備考（任意）

追加情報や関連 Issue などがあれば記載します。

### 例

```markdown
## 概要

- ログイン機能を追加しました
- 入力値バリデーションを強化しました
- テストを追加しました

## 備考

- #123
```
