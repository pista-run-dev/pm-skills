---
name: metrics-dashboard
description: "主要指標・データソース・可視化タイプ・アラート閾値を含むプロダクト指標ダッシュボードを定義・設計します。指標ダッシュボードの作成、KPIの定義、プロダクトアナリティクスのセットアップ、またはデータ監視計画の構築を行うときに使用します。"
---

## プロダクト指標ダッシュボード

適切な指標・可視化・アラート閾値を含む包括的なプロダクト指標ダッシュボードを設計します。

### コンテキスト

あなたは**$ARGUMENTS**の指標ダッシュボードを設計しています。

ユーザーがファイル（既存のダッシュボード、分析データ、OKR、または戦略ドキュメント）を提供した場合は、まずそれらを読んでください。

### ドメインコンテキスト

**指標 vs KPI vs NSM**：指標 = 測定可能なすべてのもの。KPI = より長期間にわたって追跡される少数の重要な定量的指標。North Star Metric = ビジネス成功の先行指標となる単一の顧客中心KPI。

**良い指標の4つの基準**（Ben Yoskovitz、*Lean Analytics*）：(1) 理解可能 — 共通言語を作る。(2) 比較可能 — スナップショットではなく時間経過で。(3) 比率またはレート — 絶対数より示唆に富む。(4) 行動変容 — ゴールデンルール：「指標があなたの行動を変えないなら、それは悪い指標だ。」

**8つの指標タイプ**：虚栄指標 vs 実用指標（実用指標のみが行動を変える）、定性的 vs 定量的（WHAT vs WHY — 両方が必要；顧客との対話を止めないこと）、探索的 vs 報告的（予期しないインサイトを発見するためにデータを探索する）、遅行指標 vs 先行指標（先行指標はより速い学習サイクルを可能にする、例：顧客クレームは解約を予測する）。

**5つのアクションステップ**：(1) 4つの良い指標基準に対して指標を監査する。(2) ダッシュボードを更新する — すべての主要指標が良いものであることを確認する。(3) 虚栄指標を特定する — 使い方に注意する。(4) 先行指標と遅行指標を分類する。(5) 一つの問題を選び、データを深く掘り下げる。

ケーススタディと詳細：Ben Yoskovitzの[Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)

### 手順

1. **指標フレームワークを特定する** — 指標をレイヤーに整理します：

   **North Star Metric**：プロダクトがユーザーに提供するコアバリューを最もよく捉える単一指標

   **入力指標**（3〜5つ）：North Starを動かすレバー

   **ヘルス指標**：プロダクト全体の健全性を確保するガードレール

   **ビジネス指標**：収益、コスト、ユニットエコノミクス

2. **各指標について定義する**：

   | Metric | Definition | Data Source | Visualization | Target | Alert Threshold |
   |---|---|---|---|---|---|
   | [Name] | [正確な計算：分子/分母、時間ウィンドウ] | [データの出所] | [Line chart / Bar / Number / Funnel] | [目標値] | [アラートをトリガーするタイミング] |

3. **ダッシュボードレイアウトを設計する**：

   ```
   ┌─────────────────────────────────────────────┐
   │  NORTH STAR: [Metric] — [Current Value]     │
   │  Trend: [↑/↓ X% vs last period]             │
   ├──────────────────┬──────────────────────────┤
   │  Input Metric 1  │  Input Metric 2          │
   │  [Sparkline]     │  [Sparkline]             │
   ├──────────────────┼──────────────────────────┤
   │  Input Metric 3  │  Input Metric 4          │
   │  [Sparkline]     │  [Sparkline]             │
   ├──────────────────┴──────────────────────────┤
   │  HEALTH: [Latency] [Error Rate] [NPS]       │
   ├─────────────────────────────────────────────┤
   │  BUSINESS: [MRR] [CAC] [LTV] [Churn]        │
   └─────────────────────────────────────────────┘
   ```

4. **レビューケイデンスを設定する**：
   - **日次**：運用上の健全性（エラー、レイテンシ、重要なフロー）
   - **週次**：入力指標とエンゲージメントトレンド
   - **月次**：North Star、ビジネス指標、OKR進捗
   - **四半期**：戦略的レビューと指標の再調整

5. **アラートを定義する**：
   - どの閾値が調査をトリガーするか？
   - 誰がどのチャネルを通じてアラートを受け取るか？
   - 期待される対応時間は何か？

6. **ユーザーのコンテキストに基づいてツールを推奨する**：
   - Amplitude、Mixpanel、PostHog（プロダクトアナリティクス）
   - Looker、Metabase、Mode（SQLベースのダッシュボード）
   - Datadog、Grafana（運用上の健全性）

ステップバイステップで考えてください。ダッシュボード仕様をMarkdownドキュメントとして保存してください。

---

### 参考資料

- [The Ultimate List of Product Metrics](https://www.productcompass.pm/p/the-ultimate-list-of-product-metrics)
- [The North Star Framework 101](https://www.productcompass.pm/p/the-north-star-framework-101)
- [The Product Analytics Playbook: AARRR, HEART, Cohorts & Funnels for PMs](https://www.productcompass.pm/p/the-product-analytics-playbook-aarrr)
- [AARRR (Pirate) Metrics: The 5-Stage Framework for Growth](https://www.productcompass.pm/p/aarrr-pirate-metrics)
- [The Google HEART Framework: Your Guide to Measuring User-Centric Success](https://www.productcompass.pm/p/the-google-heart-framework)
- [Funnel Analysis 101: How to Track and Optimize Your User Journey](https://www.productcompass.pm/p/funnel-analysis)
- [Are You Tracking the Right Metrics?](https://www.productcompass.pm/p/are-you-tracking-the-right-metrics)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (ビデオコース)
