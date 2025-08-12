# Contributing to AIPM v0

このプロジェクトへの貢献に感謝します！以下のガイドラインに従って、効率的なコラボレーションを行いましょう。

## 🔄 ワークフロー

### 1. ブランチ戦略
- `main`: 本番環境にデプロイ可能な安定版
- `develop`: 開発中の機能を統合するブランチ
- `feature/[機能名]`: 新機能開発用
- `hotfix/[修正内容]`: 緊急修正用

### 2. コミットメッセージ規約
```
[type]: [簡潔な説明]

詳細な説明（必要に応じて）

関連Issue: #123
```

#### Type一覧
- `feat`: 新機能追加
- `fix`: バグ修正
- `docs`: ドキュメント更新
- `refactor`: リファクタリング
- `test`: テスト追加・修正
- `chore`: その他の変更

### 3. プルリクエスト
- テンプレートに従って詳細を記載
- レビュワーを最低1名指定
- CIチェックが通過してからマージ

## 📁 ディレクトリ構造

```
aipm_v0/
├── Flow/                    # ドラフト作業領域
│   └── YYYYMM/
│       └── YYYY-MM-DD/
├── Stock/                   # 確定版ドキュメント
│   └── programs/
│       └── projects/
├── .cursor/                 # Cursor AI設定
│   └── rules/
└── docs/                    # プロジェクトドキュメント
```

## 🎯 プロジェクト管理

### Issue管理
- バグ報告は`bug`ラベル
- 新機能要求は`enhancement`ラベル
- ドキュメント関連は`documentation`ラベル

### マイルストーン
各Phaseに対応したマイルストーンを設定：
- Phase2 (2025-07 ~ 2025-09)
- Phase3 (2025-10 ~ 2025-12)

## 🔧 開発環境

### 必要なツール
- Git
- Cursor AI
- Bash/Shell環境

### セットアップ
```bash
# リポジトリクローン
git clone https://github.com/yusaku0426-algomatic/aipm_v0.git
cd aipm_v0

# 環境セットアップ
./setup_workspace_simple.sh
```

## 📋 レビューガイドライン

### コードレビュー観点
1. **機能性**: 要件を満たしているか
2. **保守性**: 理解しやすく修正しやすいか
3. **文書化**: 適切にドキュメント化されているか
4. **一貫性**: プロジェクトの規約に従っているか

### ドキュメントレビュー観点
1. **正確性**: 情報が正確で最新か
2. **完全性**: 必要な情報が網羅されているか
3. **明確性**: 読みやすく理解しやすいか
4. **構造**: 適切に構造化されているか

## 🤝 コミュニケーション

### 質問・相談
- GitHub Issuesで公開質問
- プルリクエストでコードレビュー
- Discussionsで設計相談

### 報告事項
- 重要な変更は事前にIssueで議論
- バグ発見時は速やかに報告
- セキュリティ問題は非公開で報告

## 📚 参考資料

- [PMBOK Guide](https://www.pmi.org/pmbok-guide-standards)
- [Lean UX](https://www.jeffgothelf.com/lean-ux-book/)
- [Agile Manifesto](https://agilemanifesto.org/)

---

このプロジェクトは継続的に改善されています。ガイドラインについて質問や提案があれば、Issueでお知らせください。