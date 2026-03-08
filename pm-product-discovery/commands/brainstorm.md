---
description: PM・デザイナー・エンジニアの視点から、既存製品または新製品向けのプロダクトアイデアまたは実験をブレインストーミングします
argument-hint: "[ideas|experiments] [existing|new] <製品または機能の説明>"
---

# /brainstorm -- 多視点アイデア創出

3つの視点（PM・デザイナー・エンジニア）から創造的なプロダクトアイデアまたは実験設計を生成します。既存製品に取り組んでいるか、新しいものを構築しているかに合わせて調整されます。

## 呼び出し方

```
/brainstorm ideas existing Mobile banking app engagement
/brainstorm ideas new AI-powered meal planning for busy parents
/brainstorm experiments existing Onboarding flow redesign
/brainstorm experiments new Marketplace for freelance designers
/brainstorm                          # インタラクティブモード — 何が必要かを質問します
```

## ワークフロー

### ステップ1：モードを決定する

引数を解析して2つの次元を特定します：

1. **何をブレインストーミングするか**：`ideas`（機能コンセプト）または `experiments`（検証テスト）
2. **製品ステージ**：`existing`（継続的ディスカバリー）または `new`（初期ディスカバリー）

どちらかの次元が欠けている場合はユーザーに質問します。両方欠けている場合は質問します：
- 「構築するものの**ideas**をブレインストーミングしていますか？それとも仮定を検証する**experiments**ですか？」
- 「これは**existing**製品のためですか、それとも**new**製品コンセプトのためですか？」

### ステップ2：コンテキストを収集する

ユーザーにコンテキストを質問します。会話形式で — 最も重要な質問から先に：

**既存製品の場合：**
- 製品は何ですか？現在のユーザーは誰ですか？
- どの機会領域または問題空間を探索していますか？
- 制約はありますか（技術的負債、プラットフォームの制限、チームキャパシティ）？
- 以前に試みられたことは何ですか？

**新製品の場合：**
- 製品コンセプトは何ですか？どんな問題を解決しますか？
- ターゲットユーザーは誰ですか？現在の代替手段は何ですか？
- どのステージにいますか？（ナプキンスケッチ、検証済み問題、初期プロトタイプ）
- 最もリスクの高い仮定は何ですか？

アップロードされたファイル（PRD、調査ドキュメント、戦略デッキ）、貼り付けられたテキスト、または会話からコンテキストを受け入れます。

### ステップ3：アウトプットを生成する

**アイデアをブレインストーミングする場合** — **brainstorm-ideas-existing** または **brainstorm-ideas-new** スキルを適用します：
- 3つの視点からアイデアを生成する：プロダクトマネージャー（ユーザー価値、ビジネスインパクト）、デザイナー（UX、喜び、アクセシビリティ）、エンジニア（技術革新、プラットフォーム活用、スケーラビリティ）
- 各アイデアに：名前、説明、ターゲットユーザーインパクト、実現可能性評価
- 根拠とともにトップ5のアイデアをランク付けする
- クイックウィンになりうるアイデアと戦略的な賭けになるアイデアにフラグを立てる

**実験をブレインストーミングする場合** — **brainstorm-experiments-existing** または **brainstorm-experiments-new** スキルを適用します：
- 既存製品の場合：A/Bテスト、プロトタイプ、フェイクドアテスト、ウィザード・オブ・オズ、コンシェルジュ実験、スパイクを提案する
- 新製品の場合：XYZ+S仮説を作成し、プレタイプ実験（ランディングページ、説明動画、事前注文、コンシェルジュMVP）を提案する
- 各実験に：仮説、方法、成功基準、工数見積もり、予想タイムライン
- 学習対工数比でランク付けする

### ステップ4：深掘りと反復

初期結果を提示した後、以下を提供します：
- 「これらのアイデアのいずれかを**詳細なスペック**に展開しますか？」
- 「トップアイデアの背後にある**仮定を特定**しますか？」（`identify-assumptions-existing` または `identify-assumptions-new` スキルに連鎖）
- 「トップアイデアを検証する**実験を設計**しますか？」（実験モードに連鎖）
- 「これらを現在のバックログに対して**優先順位付け**しますか？」（`prioritize-features` スキルに連鎖）

## アウトプット形式

### アイデアの場合：
```
## Brainstorm: [Product/Feature Area]
**Mode**: Ideas for [existing/new] product
**Context**: [1〜2文のまとめ]

### PM Perspective
1. **[Idea Name]** — [description] | Impact: [H/M/L] | Effort: [H/M/L]
2. ...

### Designer Perspective
1. **[Idea Name]** — [description] | Impact: [H/M/L] | Effort: [H/M/L]
2. ...

### Engineer Perspective
1. **[Idea Name]** — [description] | Impact: [H/M/L] | Effort: [H/M/L]
2. ...

### Top 5 Recommendations
| Rank | Idea | Why | Quick Win? |
|------|------|-----|------------|

### Next Steps
[これらのアイデアで何をするか]
```

### 実験の場合：
```
## Experiment Design: [Product/Feature Area]
**Mode**: Experiments for [existing/new] product

### Hypotheses
1. **[Hypothesis]** — XYZ format: [X]% of [Y] will [Z] within [S timeframe]

### Recommended Experiments
| # | Experiment | Tests Hypothesis | Method | Effort | Timeline |
|---|-----------|-----------------|--------|--------|----------|

### Experiment Details
[各実験：セットアップ、成功基準、リスク、学べること]
```

## 注意事項

- 既存製品については、現在のユーザー行動と検証済みの問題にアイデアを根付かせてください
- 新製品については、まず望ましさと実現可能性のリスクに焦点を当ててください
- ユーザーが調査ドキュメントやインタビュートランスクリプトをアップロードした場合は、ブレインストーミングの前にインサイトを抽出してください
- まず広さを、次に深さを奨励してください — 評価する前に多くのアイデアを生成してください
