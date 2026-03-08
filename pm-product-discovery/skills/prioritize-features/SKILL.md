---
name: prioritize-features
description: "インパクト・工数・リスク・戦略的整合性に基づいて機能アイデアのバックログを優先順位付けし、トップ5の推奨事項を提示します。機能バックログの優先順位付け、スコープの決定、またはプロダクトアイデアのランク付けを行うときに使用します。"
---

## 機能バックログの優先順位付け

機能アイデアのバックログを評価・ランク付けして、追求すべきトップ5を特定します。

### コンテキスト

あなたは**$ARGUMENTS**の機能の優先順位付けを支援しています。

ユーザーがファイル（スプレッドシート、バックログ、機会評価）を提供した場合は、直接読んで分析してください。

### ドメインコンテキスト

フレームワーク選択のガイダンスについては`prioritization-frameworks`スキルを参照してください。主要な推奨事項：

**Opportunity Score**（Dan Olsen、*The Lean Product Playbook*）は顧客の問題を評価するために推奨されます：Opportunity Score = Importance × (1 − Satisfaction)、0〜1に正規化。高いImportance + 低いSatisfaction = 最良の機会。**ソリューションではなく問題（機会）**を優先順位付けしてください。

**ICE**はイニシアチブの迅速なスコアリングに推奨されます：Impact（Opportunity Score × 顧客数）× Confidence × Ease。**RICE**は大規模チーム向けにReachを別の要素として追加します。

### 手順

ユーザーはプロダクト目標、望ましい成果、機能アイデアを説明します。以下のステップを実行してください：

1. **優先事項を理解する**：プロダクト目標と成功指標を確認します。

2. **各機能を以下に対して評価する**：
   - **Impact**：望ましい成果にどの程度影響するか？顧客データが利用可能な場合はOpportunity Scoreを考慮してください。
   - **Effort**：開発・デザイン・調整にどの程度必要か？
   - **Risk**：どの程度の不確実性があるか？テストが必要な仮定は何か？
   - **戦略的整合性**：プロダクトビジョンと現在の目標にどの程度適合しているか？

3. **トップ5の機能を推奨する**：
   - 明確なランキング（1〜5位）
   - 各選択の簡潔な根拠
   - 考慮されたトレードオフ
   - 優先度を下げられたものとその理由

4. **役立つ場合は優先順位付けの表として提示する**。

ステップバイステップで考えてください。アウトプットが実質的な場合はMarkdownとして保存してください。

---

### 参考資料

- [Kano Model: How to Delight Your Customers Without Becoming a Feature Factory](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [The Product Management Frameworks Compendium + Templates](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (ビデオコース)
