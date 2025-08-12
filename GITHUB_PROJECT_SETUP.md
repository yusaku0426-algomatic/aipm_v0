# GitHub プロジェクト管理セットアップガイド

このドキュメントは、AIPM v0プロジェクトのGitHub管理体制を最適化するための設定提案です。

## 🎯 推奨設定項目

### 1. GitHub Projects設定

#### Phase2プロジェクト (2025年7月-9月)
```
プロジェクト名: 鴻池運輸DX推進 Phase2
説明: 全社生成AI推進プロジェクト Phase2（健康診断OCR・規程集FAQ・KPI計測）
期間: 2025-07-01 ~ 2025-09-30
```

**ボード構成:**
- 📋 Backlog（優先度付き）
- 🔄 In Progress（WIP制限: 3）
- 👀 Review（レビュー待ち）
- ✅ Done（完了）

**カスタムフィールド:**
- Priority: High/Medium/Low
- Phase: Phase2/Phase3/Future
- Category: 技術基盤/業務ワークフロー/内製化/評価
- Estimate: 1d/3d/1w/2w/1m

### 2. Issues管理体制

#### ラベル設定
```yaml
# 種別
- name: "bug"
  color: "d73a4a"
  description: "バグ報告"

- name: "enhancement"
  color: "a2eeef"
  description: "新機能・改善"

- name: "documentation"
  color: "0075ca"
  description: "ドキュメント関連"

- name: "question"
  color: "d876e3"
  description: "質問・相談"

# 優先度
- name: "priority:high"
  color: "ff6b6b"
  description: "高優先度"

- name: "priority:medium"
  color: "ffa500"
  description: "中優先度"

- name: "priority:low"
  color: "90ee90"
  description: "低優先度"

# フェーズ
- name: "phase:2"
  color: "4caf50"
  description: "Phase2 (2025-07~09)"

- name: "phase:3"
  color: "2196f3"
  description: "Phase3 (2025-10~12)"

# カテゴリ
- name: "category:infrastructure"
  color: "795548"
  description: "技術基盤・インフラ"

- name: "category:workflow"
  color: "9c27b0"
  description: "業務ワークフロー"

- name: "category:training"
  color: "ff9800"
  description: "内製化・研修"

- name: "category:evaluation"
  color: "607d8b"
  description: "評価・分析"
```

#### マイルストーン設定
```
1. Phase2-KPI機能実装 (2025-07-31)
   - KPI計測システムの実装・稼働開始

2. Phase2-認可機能実装 (2025-08-15)
   - 権限管理システムの運用開始

3. Phase2-人事ワークフロー (2025-08-31)
   - 健康診断OCR・規程集FAQの完成

4. Phase2-本番運用開始 (2025-09-15)
   - 全ワークフローの本番稼働

5. Phase2-完了評価 (2025-09-30)
   - ROI評価レポート完成・Phase3準備
```

### 3. 自動化設定

#### GitHub Actions推奨ワークフロー

**1. ドキュメント自動検証**
```yaml
name: Document Validation
on: [push, pull_request]
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Validate Markdown
        run: |
          # Markdownファイルのリンク切れチェック
          # 必須項目の存在確認
```

**2. Issue自動ラベリング**
```yaml
name: Auto Label Issues
on:
  issues:
    types: [opened]
jobs:
  label:
    runs-on: ubuntu-latest
    steps:
      - name: Auto assign labels
        # タイトルや内容に基づいた自動ラベリング
```

### 4. ブランチ保護設定

**mainブランチ:**
- Require pull request reviews (1人以上)
- Require status checks to pass
- Require branches to be up to date
- Restrict pushes to matching branches

**developブランチ:**
- Require pull request reviews (1人以上)
- Allow force pushes (管理者のみ)

### 5. Discussion設定

**カテゴリ設定:**
- 💡 Ideas（アイデア・提案）
- ❓ Q&A（質問・回答）
- 📢 Announcements（お知らせ）
- 🎯 Project Planning（プロジェクト計画）
- 🔧 Technical Discussion（技術議論）

## 📊 推奨レポート・ダッシュボード

### 1. 進捗レポート（週次）
- 完了Issue数
- 新規Issue数
- 平均解決時間
- マイルストーン達成率

### 2. 品質メトリクス
- PRレビュー時間
- バグ発見率
- ドキュメント更新頻度

### 3. チーム活動
- コミット頻度
- レビュー参加率
- Discussion活動度

## 🚀 初期セットアップ手順

### 1. GitHub Projectsの作成
```bash
# GitHub CLIを使用した場合
gh project create "鴻池運輸DX推進 Phase2" \
  --body "全社生成AI推進プロジェクト Phase2の管理" \
  --public
```

### 2. ラベル一括作成
```bash
# labels.jsonを作成後
gh label create -R yusaku0426-algomatic/aipm_v0 \
  --file labels.json
```

### 3. マイルストーン作成
```bash
gh milestone create "Phase2-KPI機能実装" \
  --due-date 2025-07-31 \
  --description "KPI計測システムの実装・稼働開始"
```

## 📝 運用ルール

### Issue作成時
1. 適切なテンプレートを選択
2. 必須ラベルを付与
3. マイルストーンを設定
4. 担当者をアサイン（可能であれば）

### PR作成時
1. テンプレートに従って記載
2. 関連Issueをリンク
3. レビュワーを指定
4. 適切なラベルを付与

### 定期レビュー
- **毎週月曜**: 進捗レビュー・優先度調整
- **毎月末**: マイルストーン達成度評価
- **Phase完了時**: 総合評価・次Phase計画

## 🔗 参考リンク

- [GitHub Projects Documentation](https://docs.github.com/en/issues/planning-and-tracking-with-projects)
- [GitHub Issues Documentation](https://docs.github.com/en/issues)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

---

このセットアップガイドに基づいて、効率的なプロジェクト管理体制を構築しましょう。