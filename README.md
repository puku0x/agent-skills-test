# agent-skills-test

GitHub Copilot および Claude Code 用の Agent Skills のテスト用リポジトリです。

## 概要

このリポジトリは、GitHub Copilot と Claude Code 用の Agent Skills を提供します。

## 利用可能なスキル

### Git & GitHub ワークフロー

#### `/git-commit`

Conventional Commits 形式のコミットメッセージを自動生成します。

- **機能**: ステージされた変更に基づいて、適切なタイプとスコープを自動判定
- **使用場面**: コミット作成、コミットメッセージ作成
- **参照**: [.github/skills/git-commit/SKILL.md](.github/skills/git-commit/SKILL.md)

#### `/git-branch`

プロジェクトの命名規則に従った Git ブランチを作成します。

- **機能**: 変更内容に基づいてブランチタイプを自動判定
- **使用場面**: ブランチ作成、新しいブランチへの切り替え
- **参照**: [.github/skills/git-branch/SKILL.md](.github/skills/git-branch/SKILL.md)

#### `/gh-pr`

適切なフォーマットで GitHub Pull Request を作成します。

- **機能**: PR タイトルとテンプレートの自動生成（日本語対応）
- **使用場面**: PR 作成、変更のレビュー依頼
- **参照**: [.github/skills/gh-pr/SKILL.md](.github/skills/gh-pr/SKILL.md)

#### `/gh-default-branch`

GitHub CLI を使用してデフォルトブランチ名を取得します。

- **機能**: `gh` コマンドでデフォルトブランチ名（`main`, `master`, `develop` など）を取得
- **使用場面**: PR 作成時、ブランチ比較時、ベースブランチのチェックアウト時
- **参照**: [.github/skills/gh-default-branch/SKILL.md](.github/skills/gh-default-branch/SKILL.md)

## プロジェクト構造

```
.
├── .claude/
│   ├── commands/                    # Claude Code スラッシュコマンド（.github/prompts をロード）
│   │   └── create-pull.md
│   └── skills/                      # Claude Code Agent Skills（.github/skills をロード）
│       ├── git-commit/
│       │   └── SKILL.md
│       ├── git-branch/
│       │   └── SKILL.md
│       ├── gh-pr/
│       │   └── SKILL.md
│       └── gh-default-branch/
│           └── SKILL.md
├── .github/
│   ├── skills/                      # GitHub Copilot Agent Skills ディレクトリ
│   │   ├── git-commit/              # Conventional Commits スキル
│   │   │   ├── SKILL.md
│   │   │   └── references/
│   │   │       └── commit-message.instructions.md
│   │   ├── git-branch/              # Git ブランチ作成スキル
│   │   │   ├── SKILL.md
│   │   │   └── references/
│   │   │       └── branch-name.md
│   │   ├── gh-pr/                   # GitHub PR 作成スキル
│   │   │   ├── SKILL.md
│   │   │   └── references/
│   │   │       └── pull-request-description.instructions.md
│   │   └── gh-default-branch/       # デフォルトブランチ取得スキル
│   │       └── SKILL.md
│   ├── prompts/                     # GitHub Copilot スラッシュコマンド
│   │   └── create-pull.prompt.md
│   ├── copilot-instructions.md      # GitHub Copilot カスタムインストラクション
│   └── PULL_REQUEST_TEMPLATE.md     # PR テンプレート
├── CLAUDE.md                        # Claude Code カスタムインストラクション（.github/copilot-instructions.md をロード）
└── README.md                        # このファイル
```

## 使用方法

Agent Skills はスラッシュコマンドまたは AI エージェントとのチャットやプロンプト内で自動的に起動されます。

## 必要なツール

このリポジトリのスキルを使用するには、以下のツールが必要です：

- [Git](https://git-scm.com/) - バージョン管理
- [GitHub CLI](https://cli.github.com/) - GitHub 操作（`gh-pr`、`gh-default-branch` スキル）

## ライセンス

このプロジェクトは [MIT ライセンス](LICENSE.txt) です。

## 参考資料

- [Agent Skills Specification](https://agentskills.io/specification)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub CLI Documentation](https://cli.github.com/)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [Claude Code Documentation](https://claude.ai/code)
