# GitHub Actions ワークフロー

このディレクトリには、開発効率化のためのGitHub Actionsワークフローが含まれています。

## ワークフロー詳細

### auto-assign.yml
**目的**: PRの自動アサイン  
**トリガー**: PR作成時  
**動作**: 作成者を自動的にPRにアサイン

### auto-label.yml
**目的**: キーワードベースの自動ラベル付け  
**トリガー**: PR/イシュー作成・編集時  
**動作**: タイトル・本文のキーワードから適切なラベルを自動付与

**検出キーワード**:
- `bug`, `error`, `fix` → `bug` ラベル
- `feature`, `add`, `new` → `enhancement` ラベル
- `doc`, `readme` → `documentation` ラベル
- `test`, `spec` → `test` ラベル
- `refactor`, `cleanup` → `refactor` ラベル
- `security` → `security` ラベル
- `performance`, `optimize` → `performance` ラベル

### code-quality.yml
**目的**: 多言語対応のコード品質チェック  
**トリガー**: `main`, `develop` ブランチへのプッシュ・PR  
**動作**: プロジェクトの言語を自動検出し、適切な品質チェックを実行

**対応言語**:
- **Node.js** (package.json): ESLint, Prettier, TypeScript, テスト
- **Python** (requirements.txt/pyproject.toml): Black, isort, flake8, pytest
- **Rust** (Cargo.toml): rustfmt, clippy, cargo test
- **Go** (go.mod): gofmt, go vet, go test

### dependabot-auto-merge.yml
**目的**: Dependabotによる依存関係更新の自動マージ  
**トリガー**: Dependabot PRの作成・更新  
**動作**: マイナーアップデート・セキュリティパッチを自動承認・マージ

**自動マージ条件**:
- PR作成者が `dependabot[bot]`
- タイトルに `minor` または `patch` を含む
- タイトルに `security` を含む

## 権限設定

各ワークフローには適切な権限が設定されています：

- `contents: write` - コードの読み取り・書き込み
- `issues: write` - イシューへの書き込み  
- `pull-requests: write` - PRへの書き込み

## カスタマイズ

個人開発での使用を想定しており、必要に応じて以下をカスタマイズできます：

- **auto-label.yml**: キーワード・ラベルの追加
- **code-quality.yml**: 言語固有の設定変更
- **dependabot-auto-merge.yml**: 自動マージ条件の調整