---
name: prioritize-assumptions
description: "インパクト×リスクマトリクスを使って仮定を優先順位付けし、各仮定に対する実験を提案します。仮定のリストをトリアージするとき、最初に何をテストするか決めるとき、または仮定優先順位付けキャンバスを適用するときに使用します。"
---

## 仮定の優先順位付け

インパクト×リスクマトリクスを使って仮定をトリアージし、対象を絞った実験を提案します。

### コンテキスト

あなたは**$ARGUMENTS**の仮定の優先順位付けを支援しています。

ユーザーが仮定や調査データを含むファイルを提供した場合は、まずそれらを読んでください。

### ドメインコンテキスト

**ICE**は仮定の優先順位付けに適しています：Impact（Opportunity Score × 顧客数）× Confidence（1〜10）× Ease（1〜10）。Opportunity Score = Importance × (1 − Satisfaction)、0〜1に正規化（Dan Olsen）。**RICE**はImpactをReachとImpactに分けます：(R × I × C) / E。完全な式とテンプレートについては`prioritization-frameworks`スキルを参照してください。

### 手順

ユーザーは優先順位付けする仮定のリストを提供します。以下のフレームワークを適用してください：

1. **各仮定について**、2つの次元を評価します：
   - **Impact**：この仮定を検証することで生まれる価値 AND 影響を受ける顧客数（ICEでは：Impact = Opportunity Score × 顧客数）
   - **Risk**：(1 - Confidence) × Effortとして定義

2. **インパクト×リスクマトリクスを使って各仮定を分類する**：
   - **低インパクト、低リスク** → 優先度の高い仮定が対処されるまでテストを延期する
   - **高インパクト、低リスク** → 実装に進む（低リスク、高報酬）
   - **低インパクト、高リスク** → アイデアを却下する（投資に見合わない）
   - **高インパクト、高リスク** → テストする実験を設計する

3. **テストが必要な各仮定について**、以下を満たす実験を提案します：
   - 最小限の工数で検証済み学習を最大化する
   - 意見ではなく実際の行動を測定する
   - 明確な成功指標と閾値がある

4. **結果を**優先順位付けされたマトリクスまたは表として提示します。

ステップバイステップで考えてください。アウトプットが実質的な場合はMarkdownとして保存してください。

---

### 参考資料

- [Assumption Prioritization Canvas: How to Identify And Test The Right Assumptions](https://www.productcompass.pm/p/assumption-prioritization-canvas)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (ビデオコース)
