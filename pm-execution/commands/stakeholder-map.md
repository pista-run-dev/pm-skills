---
description: Power × Interestグリッドでステークホルダーをマッピングし、カスタマイズされたコミュニケーション計画を作成する
argument-hint: "<project, initiative, or launch>"
---

# /stakeholder-map -- ステークホルダーマッピングとコミュニケーション計画

プロジェクトのすべてのステークホルダーを特定し、影響力と関心度でマッピングし、適切な人が適切な情報を適切なタイミングで受け取れるコミュニケーション計画を生成します。

## 呼び出し方

```
/stakeholder-map New analytics platform launch
/stakeholder-map Pricing model change affecting all customers
/stakeholder-map [upload a project brief or org chart]
```

## ワークフロー

### ステップ1：イニシアチブを理解する

以下を質問する：
- プロジェクトまたはイニシアチブは何か？
- どのフェーズにあるか？（計画、構築、ローンチ、ローンチ後）
- すでに知っている明らかなステークホルダーは誰か？
- 注意すべき政治的にデリケートなダイナミクスはあるか？

### ステップ2：ステークホルダーを特定する

ユーザーが考えていないかもしれないステークホルダーをブレインストーミングする：
- **社内**：エンジニアリング、デザイン、QA、データ、法務、財務、マーケティング、セールス、サポート、リーダーシップ
- **社外**：顧客、パートナー、ベンダー、規制当局、ボードメンバー
- **見落とされやすい**：隣接するチーム、オンコールエンジニア、カスタマーサクセス、ドキュメンテーションチーム

### ステップ3：Power × Interestグリッドにマッピングする

**stakeholder-map**スキルを適用する：

各ステークホルダーを象限に配置する：

```
                    HIGH INTEREST
                         │
    KEEP SATISFIED       │      MANAGE CLOSELY
    (High Power,         │      (High Power,
     Low Interest)       │       High Interest)
                         │
   ──────────────────────┼──────────────────────
                         │
    MONITOR              │      KEEP INFORMED
    (Low Power,          │      (Low Power,
     Low Interest)       │       High Interest)
                         │
                    LOW INTEREST
```

### ステップ4：コミュニケーション計画を生成する

```
## Stakeholder Map: [Initiative]

### Stakeholder Grid
| Stakeholder | Role | Power | Interest | Quadrant | Stance |
|------------|------|-------|----------|----------|--------|

### Communication Plan

#### Manage Closely (High Power, High Interest)
| Stakeholder | Channel | Frequency | Content | Owner |
|------------|---------|-----------|---------|-------|

#### Keep Satisfied (High Power, Low Interest)
| Stakeholder | Channel | Frequency | Content | Owner |
|------------|---------|-----------|---------|-------|

#### Keep Informed (Low Power, High Interest)
| Stakeholder | Channel | Frequency | Content | Owner |
|------------|---------|-----------|---------|-------|

#### Monitor (Low Power, Low Interest)
[最小限のコミュニケーション——広範な更新にのみ含める]

### Potential Conflicts
[ステークホルダーの利益が衝突する可能性のある箇所——軽減戦略とともに]

### Escalation Path
[決定がブロックされたときに誰に相談するか]

### RACI Matrix
| Decision Area | Responsible | Accountable | Consulted | Informed |
|--------------|-------------|-------------|-----------|----------|
```

markdownとして保存する。

### ステップ5：次のステップを提案する

- 「「Manage Closely」グループへの**最初のステークホルダー更新を起草**したいですか？」
- 「主要ステークホルダーとの会話のための**ミーティング準備ブリーフを作成**しましょうか？」
- 「繰り返しチェックリストとして**コミュニケーションケイデンスを設定**しましょうか？」

## 注意事項

- 「Manage Closely」象限はPMが最も政治的資本を費やす場所——これらの関係を正しく構築する
- 「Stance」（支持的、中立的、抵抗的）は関係構築への投資をどこに優先するかを判断するのに役立つ
- 下流のステークホルダーを忘れない：サポート、ドキュメント、セールスイネーブルメントチームはローンチに驚かされることが多い
- プロジェクトの進化に合わせてマップを更新する——ステークホルダーの関心はプロジェクトフェーズによって変わる
