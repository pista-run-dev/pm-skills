---
description: 機能ベースのロードマップを、戦略的意図を伝えるアウトカム中心のロードマップに変換する
argument-hint: "<roadmap as text, file, or list of planned features>"
---

# /transform-roadmap -- アウトカム中心のロードマップ

計画された機能のリストやアウトプット中心のロードマップを受け取り、*何を*ではなく*なぜ*を伝えるアウトカム中心のロードマップとして書き直します。

## 呼び出し方

```
/transform-roadmap [paste your feature list or roadmap]
/transform-roadmap [upload a roadmap doc, spreadsheet, or screenshot]
```

## ワークフロー

### ステップ1：現在のロードマップを受け取る

以下のあらゆる形式で受け付ける：
- 機能リストまたはバックログアイテム
- ロードマップドキュメント（Now/Next/Later、四半期別、タイムライン）
- スプレッドシートまたはガントチャートのエクスポート
- ロードマップツールのスクリーンショット

各アイテムを解析して、機能名、説明、ターゲット日付/タイムフレーム、コンテキストを抽出する。

### ステップ2：戦略的コンテキストを理解する

以下を質問する：
- この期間のプロダクト目標またはOKRは何か？
- このロードマップの対象者は誰か？（エグゼクティブ、エンジニアリング、顧客、ボード）
- どのフォーマットが好ましいか？（Now/Next/Later、四半期別、タイムライン）

### ステップ3：各アイテムを変換する

**outcome-roadmap**スキルを適用する：

ロードマップの各機能/アウトプットに対して：
1. 達成しようとしている**ユーザーまたはビジネスのアウトカム**を特定する
2. アウトカムステートメントとして書き直す：「[Verb] [metric/experience] for [user segment]」
3. 同じアウトカムに貢献する機能を1つのイニシアチブにグループ化する
4. 各アウトカムに成功指標を追加する

**Before → After の例：**
- 「Build SSO integration」→「Reduce enterprise onboarding friction — target: 50% faster time-to-first-value for enterprise accounts」
- 「Redesign dashboard」→「Help power users find insights faster — target: 30% reduction in time-to-insight」
- 「Add CSV export」→「Enable teams to share data outside the product — target: 25% increase in report sharing」

### ステップ4：変換されたロードマップを生成する

```
## Outcome-Focused Roadmap: [Product] — [Period]

**Strategic themes**: [2-3 high-level themes]

### Now (Current Quarter)
**Theme: [Strategic Theme]**
| Outcome | Success Metric | Key Initiatives | Status |
|---------|---------------|----------------|--------|

### Next (Next Quarter)
**Theme: [Strategic Theme]**
| Outcome | Success Metric | Key Initiatives | Confidence |
|---------|---------------|----------------|------------|

### Later (Future)
**Theme: [Strategic Theme]**
| Outcome | Success Metric | Key Initiatives | Dependencies |
|---------|---------------|----------------|-------------|

### Transformation Notes
| Original Feature | Transformed Outcome | Why This Framing |
|-----------------|--------------------|-----------------|

### What Changed
[ロードマップのナラティブがどのように変わったかのサマリー]
```

markdownファイルとして保存する。

### ステップ5：レビュー

以下を提案する：
- 「各アウトカムに**OKR整合を追加**しましょうか？」
- 「このロードマップの**ステークホルダープレゼンテーションを起草**しましょうか？」
- 「Nowアイテムの**リスクを特定**しましょうか？」

## 注意事項

- アウトカムは測定可能で明確な「完了」状態を持つべき
- 複数の機能が1つのアウトカムにマッピングできる——これは欠陥ではなく特徴
- アウトプットが明確にアウトカムに貢献していない場合は、ユーザーに正当化または優先度引き下げを求めるフラグを立てる
- 対象者が重要：エグゼクティブ向けロードマップはアウトカムのみ、エンジニアリング向けロードマップは各アウトカムの下に成果物を含められる
- 「Later」アイテムは具体性を下げるべき——コミットされたソリューションなしのアウトカム
