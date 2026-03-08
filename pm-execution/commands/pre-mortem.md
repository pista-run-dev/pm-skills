---
description: PRD、ローンチ計画、または機能のプレモーテムリスク分析を実施する——問題が起きる前に何が間違いになりうるかを特定する
argument-hint: "<PRD, plan, or feature description>"
---

# /pre-mortem -- ローンチ前リスク分析

ローンチが失敗したと想像してください。次に、なぜそうなったかを逆算して考えます。このコマンドはTigers/Paper Tigers/Elephantsフレームワークを適用して、実際のリスクを表面化し軽減計画を作成します。

## 呼び出し方

```
/pre-mortem [paste or upload a PRD, launch plan, or feature spec]
/pre-mortem We're launching a self-serve billing portal next month
```

## ワークフロー

### ステップ1：計画を受け取る

以下の形式で受け付ける：PRD、機能仕様、ローンチ計画、プロジェクトブリーフ、または口頭による説明。詳細が多いほど、リスク分析がより精確になる。

### ステップ2：リスク特定

**pre-mortem**スキルを適用する：

プロダクトがローンチして失敗したと想像する。カテゴリ別にリスクを生成する：
- **技術的**：パフォーマンス、スケーラビリティ、統合の失敗、データの問題
- **ユーザー**：採用の障壁、ユーザビリティの問題、期待に応えられないこと
- **ビジネス**：収益への影響、競合他社の反応、市場タイミング
- **運用的**：サポート負荷、ドキュメントのギャップ、トレーニングの必要性
- **依存関係**：サードパーティサービス、クロスチームの引き渡し、規制

### ステップ3：リスクを分類する

各リスクを分類する：

**Tigers** — 失敗を引き起こす可能性がある実際の、実質的なリスク
- 深刻度を評価：ローンチブロッキング / ファストフォロー / トラック
- ローンチブロッキングのTigers：即時の軽減が必要
- ファストフォローのTigers：ローンチ後の最初のスプリント内に対処する計画
- トラックのTigers：監視するがローンチを遅らせない

**Paper Tigers** — 怖く感じるが過大評価されているリスク
- なぜ懸念が管理可能かを説明する
- これが本当のTigerになるためには何が変わる必要があるかを記録する

**Elephants** — チームが認識しているが議論を避けているリスク
- 政治的、組織的、または不快なリスクを表面化する
- 提案された会話の出発点とともに建設的にフレーミングする

### ステップ4：プレモーテムレポートを生成する

```
## Pre-Mortem: [Feature/Launch]

**Date**: [today]
**Status**: [Draft / Reviewed]

### Risk Summary
- **Tigers**: [count] ([launch-blocking], [fast-follow], [track])
- **Paper Tigers**: [count]
- **Elephants**: [count]

### Launch-Blocking Tigers
| # | Risk | Likelihood | Impact | Mitigation | Owner | Deadline |
|---|------|-----------|--------|-----------|-------|----------|

### Fast-Follow Tigers
| # | Risk | Likelihood | Impact | Planned Response | Owner |
|---|------|-----------|--------|-----------------|-------|

### Track Tigers
[ローンチ後に監視するリスクとトリガー条件]

### Paper Tigers
[大きく見えるが管理可能な懸念——理由とともに]

### Elephants in the Room
[チームが議論すべき不都合な真実]

### Go/No-Go Checklist
- [ ] All launch-blocking Tigers mitigated
- [ ] Fast-follow plan documented and assigned
- [ ] Monitoring in place for Track Tigers
- [ ] Rollback plan defined
- [ ] Support team briefed
```

markdownとして保存する。

### ステップ5：次のステップを提案する

- 「リスク軽減策を含めて**PRDを更新**したいですか？」
- 「最もリスクの高いエリアの**テストシナリオを作成**しましょうか？」
- 「これらの調査結果から**ローンチチェックリストを起草**しましょうか？」

## 注意事項

- 最良のプレモーテムは計画が80%完成したときに実施する——方向転換できるほど早く、実質がある程度遅い
- 明らかなリスクを超えて押し進める——最も危険なリスクは誰も言及しないもの
- Elephantsが最も価値ある出力——チームが議論を避けていることを表面化する
- 各Tigerに対して、軽減策は具体的で割り当て可能であるべきで、「注意する」ではない
- プレモーテムがローンチブロッキングのTigersが多すぎることを明らかにした場合は、ローンチを延期または段階化することを推奨する
