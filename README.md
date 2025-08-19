# CIT - Claude Integration Tools

GitHub運用とClaude Code連携のためのリポジトリです。

## Claude Code連携

このリポジトリは Claude Code GitHub App と連携して、イシューやプルリクエストから直接 Claude Code に指示を出すことができます。

### 使用方法

#### イシューから指示を出す

1. 「Claude Code タスク」テンプレートでイシューを作成
2. イシューの本文に `@claude [指示内容]` を記載
3. 自動的にClaude Codeが実行され、PRが作成されます

**例:**
```
@claude READMEにインストール手順を追加してください
```

#### プルリクエストから指示を出す

1. プルリクエストのコメントで `@claude [指示内容]` を投稿
2. 自動的にClaude Codeが実行され、新しいPRが作成されます

## 機能

### 🤖 Claude Code 連携
GitHub App による自動実行（設定済み）

### 🔄 自動化
- **GitHub Actions**: PR自動アサイン、ラベル付け、コード品質チェック、Dependabot自動マージ  
  詳細: [.github/workflows/README.md](.github/workflows/README.md)
- **Dependabot**: 週次での依存関係自動更新

### 📋 テンプレート
- **イシュー**: バグ報告、機能要求、Claude Code タスク  
  詳細: [.github/ISSUE_TEMPLATE/README.md](.github/ISSUE_TEMPLATE/README.md)
- **PR**: 統一テンプレート

## 運用フロー

1. **タスク開始**: 「Claude Code タスク」テンプレートでイシュー作成  
2. **実装指示**: `@claude [具体的な指示内容]` を記載
4. **自動実行**: Claude Code が自動実行してPR作成
5. **レビュー・マージ**: 作成されたPRを確認してマージ

## カスタマイズ

個人開発向けのカジュアル運用に最適化済み。設定ファイルは必要に応じてカスタマイズ可能。