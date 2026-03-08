---
name: prioritization-frameworks
description: "式、使用タイミングガイダンス、テンプレートを含む9つの優先順位付けフレームワークのリファレンスガイド——RICE、ICE、Kano、MoSCoW、Opportunity Score、など。優先順位付け方法の選択、RICEとICEなどのフレームワークの比較、または異なる優先順位付けアプローチの仕組みを学ぶ際に使用します。"
---

## 優先順位付けフレームワークリファレンス

コンテキストに適した優先順位付けフレームワークを選択・適用するためのリファレンスガイド。

### 核心原則

顧客にソリューションを設計させないこと。機能ではなく**問題（機会）**を優先する。

### Opportunity Score（Dan Olsen、『The Lean Product Playbook』）

顧客の問題を優先するための推奨フレームワーク。

各ニーズについて顧客の**Importance**（重要度）と**Satisfaction**（満足度）を調査（0〜1スケールに正規化）。

3つの関連する式：
- **Current value** = Importance × Satisfaction
- **Opportunity Score** = Importance × (1 − Satisfaction)
- **Customer value created** = Importance × (S2 − S1)（S1 = 前の満足度、S2 = 後の満足度）

高いImportance + 低いSatisfaction = 最高のOpportunity Score = 最良の機会。Importance対Satisfactionチャートにプロット——左上象限がスイートスポット。顧客の問題を優先し、ソリューションではない。

### ICEフレームワーク

イニシアチブとアイデアの優先順位付けに有用。価値だけでなくリスクと経済的要因も考慮。

- **I**（Impact）= Opportunity Score × 影響を受ける顧客数
- **C**（Confidence）= どれくらい確信があるか？（1〜10）。リスクを考慮。
- **E**（Ease）= 実装はどれくらい簡単か？（1〜10）。経済的要因を考慮。

**Score** = I × C × E。高いほど先に優先する。

### RICEフレームワーク

ICEのImpactを2つの別々の要因に分割。より詳細さが必要な大規模チームに有用。

- **R**（Reach）= 影響を受ける顧客数
- **I**（Impact）= Opportunity Score（顧客1人あたりの価値）
- **C**（Confidence）= どれくらい確信があるか？（0〜100%）
- **E**（Effort）= 実装にどれくらい労力がかかるか？（人月）

**Score** = (R × I × C) / E

### 9つのフレームワーク概要

| Framework | Best For | Key Insight |
|-----------|----------|-------------|
| Eisenhower Matrix | 個人的なタスク | 緊急 vs 重要——個々のPMタスク管理のため |
| Impact vs Effort | タスク/イニシアチブ | シンプルな2×2——戦略的決定ではなく迅速なトリアージ |
| Risk vs Reward | イニシアチブ | Impact vs Effortに似ているが不確実性を考慮 |
| **Opportunity Score** | 顧客の問題 | **推奨。** Importance × (1 − Satisfaction)。0〜1に正規化。 |
| Kano Model | 期待の理解 | Must-be、Performance、Attractive、Indifferent、Reverse。優先順位付けではなく理解のため。 |
| Weighted Decision Matrix | 多要因の決定 | 基準に重みを割り当て、各オプションをスコア化。ステークホルダーのバイインに有用。 |
| **ICE** | アイデア/イニシアチブ | Impact × Confidence × Ease。迅速な優先順位付けに推奨。 |
| **RICE** | 規模のあるアイデア | (Reach × Impact × Confidence) / Effort。ICEにReachを追加。 |
| MoSCoW | 要件 | Must/Should/Could/Won't。注意：プロジェクト管理起源。 |

### テンプレート

- [Opportunity Score intro (PDF)](https://drive.google.com/file/d/1ENbYPmk1i1AKO7UnfyTuULL5GucTVufW/view)
- [Importance vs Satisfaction Template — Dan Olsen (Google Slides)](https://docs.google.com/presentation/d/1jg-LuF_3QHsf6f1nE1f98i4C0aulnRNMOO1jftgti8M/edit#slide=id.g796641d975_0_3)
- [ICE Template (Google Sheets)](https://docs.google.com/spreadsheets/d/1LUfnsPolhZgm7X2oij-7EUe0CJT-Dwr-/edit?usp=share_link&ouid=111307342557889008106&rtpof=true&sd=true)
- [RICE Template (Google Sheets)](https://docs.google.com/spreadsheets/d/1S-6QpyOz5MCrV7B67LUWdZkAzn38Eahv/edit?usp=sharing&ouid=111307342557889008106&rtpof=true&sd=true)

---

### 参考資料

- [The Product Management Frameworks Compendium + Templates](https://www.productcompass.pm/p/the-product-frameworks-compendium)
- [Kano Model: How to Delight Your Customers Without Becoming a Feature Factory](https://www.productcompass.pm/p/kano-model-how-to-delight-your-customers)
- [Continuous Product Discovery Masterclass (CPDM)](https://www.productcompass.pm/p/cpdm)（動画コース）
