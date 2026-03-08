---
description: North Star指標・入力指標・ヘルス指標・アラート閾値を含むプロダクト指標ダッシュボードを設計します
argument-hint: "<製品または機能領域>"
---

# /setup-metrics -- プロダクト指標ダッシュボードの設計

製品または機能の包括的な指標フレームワークを設計します — 適切なNorth Starの選択から、問題を早期に発見するアラート閾値の定義まで。

## 呼び出し方

```
/setup-metrics SaaS project management tool
/setup-metrics New checkout flow we just launched
/setup-metrics             # 何を測定するかを質問します
```

## ワークフロー

### ステップ1：何を測定するかを理解する

ユーザーに質問します：
- どの製品または機能領域の指標をセットアップしていますか？
- どのステージにありますか？（ローンチ前、最近ローンチ、成熟）
- 現在のビジネス目標またはOKRは何ですか？
- 既存の指標はありますか？何が欠けているか壊れていますか？
- どの分析ツールを使用していますか？（実装アドバイスを調整するのに役立つ）

### ステップ2：指標フレームワークを定義する

**metrics-dashboard** スキルを適用します：

**North Star Metric：**
- 製品がユーザーに提供する価値を最もよく捉える単一指標を特定する
- 基準に対して検証する：価値提供を測定する、先行指標である、アクション可能である
- 指標を正確に定義する（式、データソース、時間ウィンドウ）

**入力指標（3〜5つ）：**
- North Starを動かすレバーを特定する
- 各入力指標はチームが直接アクション可能であるべき
- 因果連鎖をマッピングする：入力 → North Star → ビジネス成果

**ヘルス指標（3〜5つ）：**
- 安定を保つべき指標 — 低下する場合は何かが問題
- 例：エラー率、レイテンシ、サポートチケット量、NPS、解約率
- 「健全な」範囲と低下閾値を定義する

**カウンター指標（1〜2つ）：**
- 間違った方向に最適化していることを示す可能性がある指標
- 例：North StarがDAUの場合、カウンター指標は空のエンゲージメントを防ぐための「セッション品質」

### ステップ3：アラート閾値を設計する

各指標について：

| Metric | Green | Yellow | Red | Check Frequency |
|--------|-------|--------|-----|----------------|
| [metric] | [健全な範囲] | [警告] | [重大] | [日次/週次] |

- **Yellow**：調査 — 何かがおかしいかもしれない
- **Red**：即時対応 — 誰かに呼びかけるかエスカレートする

### ステップ4：ダッシュボード仕様を作成する

```
## Metrics Dashboard: [Product/Feature]

**North Star**: [metric name]
**Definition**: [正確な式]
**Current value**: [分かれば]
**Target**: [目標]

### Input Metrics
| Metric | Definition | Owner | Target | Current |
|--------|-----------|-------|--------|---------|

### Health Metrics
| Metric | Healthy Range | Yellow Threshold | Red Threshold |
|--------|-------------|-----------------|---------------|

### Counter-Metrics
| Metric | Why It Matters | Watch For |
|--------|---------------|-----------|

### Metrics Tree
North Star: [metric]
├── Input: [metric 1] → driven by [team/action]
├── Input: [metric 2] → driven by [team/action]
├── Input: [metric 3] → driven by [team/action]
└── Counter: [metric] → watch for [degradation signal]

### Implementation Notes
- Data sources: [各指標のデータソース]
- Refresh frequency: [リアルタイム / 毎時 / 日次]
- Tool recommendations: [ユーザーのスタックに基づく]

### Review Cadence
- **Daily**: North Starとヘルス指標を確認する
- **Weekly**: 入力指標のトレンドをレビューし、チームスタンドアップで議論する
- **Monthly**: 深掘り — 入力はNorth Starを期待通りに動かしているか？
- **Quarterly**: 指標フレームワーク自体を再評価する
```

Markdownファイルとしてユーザーのワークスペースに保存します。

### ステップ5：次のステップを提案する

- 「これらの指標を計算する**SQLクエリを書き**ますか？」
- 「この指標フレームワークに基づいて**OKRを作成**しますか？」
- 「現実的なベースラインを設定するための**コホート分析を構築**しますか？」
- 「**週次指標レビューテンプレートをセットアップ**しますか？」

## 注意事項

- 良いNorth Starは稀です — ほとんどのチームは虚栄指標を選びます。エンゲージメントだけでなく、*ユーザーへの価値提供*を捉える指標を押し進めてください
- 入力指標はNorth Starを説明する上でMECE（相互に排他的で、集合的に網羅的）であるべきです
- 製品がローンチ前の場合は、今すぐ指標を定義しますが、ローンチ後にベースラインの調整が必要なことを記しておいてください
- カウンター指標はグッドハートの法則を防ぎます — 指標が目標になると、良い指標ではなくなります
- 誰もチェックしない散漫なダッシュボードよりも、少数の指標をしっかり計装することを推奨してください
