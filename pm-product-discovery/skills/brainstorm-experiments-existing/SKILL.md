---
name: brainstorm-experiments-existing
description: "既存製品の仮定をテストする実験（プロトタイプ、A/Bテスト、スパイクなど低コストの検証方法）を設計します。仮定の検証、機能アイデアを低コストでテストするとき、またはプロダクト実験の計画を立てるときに使用します。"
---

## 実験の設計（既存製品）

完全な実装にコミットする前に、製品の仮定をテストするための低工数の実験を設計します。

### コンテキスト

あなたはプロダクトチームが**$ARGUMENTS**の実験を設計するのを支援しています。チームは機能アイデアと検証が必要な仮定を持っています。

ユーザーがファイル（PRD、仮定リスト、デザイン）を提供した場合は、まずそれらを読んでください。

### 手順

ユーザーはアイデアと仮定を説明します。以下のステップを実行してください：

1. **アイデアと仮定を明確にする**：チームが構築したいものと検証が必要なことを確認します。

2. **各仮定に対する実験を提案する**。以下のような方法を検討してください：
   - プロトタイプを使ったファーストクリックテストまたはタスク完了テスト
   - 機能スタブまたはフェイクドアテスト
   - テクニカルスパイク
   - 本番環境でのA/Bテスト（リスク軽減策を含む）
   - ウィザード・オブ・オズアプローチ
   - 調査ベースの検証（意見ではなく行動ベース）

3. **従うべき主要原則**：
   - ユーザーの意見ではなく、実際の行動を測定してください
   - 責任を持ってテストしてください。ユーザーやビジネスをリスクにさらさないでください
   - 本番テスト（例：A/Bテスト）については、リスク軽減戦略を説明してください
   - 最小限の工数で最大限の検証済み学習を目指してください

4. **各実験について**、以下を明記してください：
   - **仮定**：何を信じているか？
   - **実験**：それを検証するために正確に何をするか？
   - **指標**：何を測定するか？
   - **成功閾値**：正しい場合の期待値

ステップバイステップで考えてください。実験を明確な表または構造化された形式で提示してください。実質的な場合はMarkdownとして保存してください。

---

### 参考資料

- [Testing Product Ideas: The Ultimate Validation Experiments Library](https://www.productcompass.pm/p/the-ultimate-experiments-library)
- [Assumption Prioritization Canvas: How to Identify And Test The Right Assumptions](https://www.productcompass.pm/p/assumption-prioritization-canvas)
- [What Is Product Discovery? The Ultimate Guide Step-by-Step](https://www.productcompass.pm/p/what-exactly-is-product-discovery)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm) (ビデオコース)
