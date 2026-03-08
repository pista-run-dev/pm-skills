---
description: 会社の目標に沿ったチームレベルのOKRをブレインストーミングする——定性的な目標と測定可能なキー・リザルト
argument-hint: "<team, product area, or company objective>"
---

# /plan-okrs -- チームOKR計画

チームの作業を会社の戦略に結びつける、よく構造化されたOKRを生成します。定性的な目標と定量的なキー・リザルトを持つ3つのOKRセットを作成します。

## 呼び出し方

```
/plan-okrs Growth team Q2 — company goal is 50% ARR increase
/plan-okrs Onboarding squad aligned to "improve activation rate"
/plan-okrs [upload company OKRs or strategy doc]
```

## ワークフロー

### ステップ1：コンテキストを収集する

ユーザーに質問する：
- これらのOKRはどのチームまたはプロダクトエリアのためのものか？
- 何の期間？（四半期が標準だが、年間またはカスタムもある）
- これが達成すべき会社レベルの目標は何か？
- 前の四半期に何があったか？（達成、未達、学び）
- 制約や既知の優先事項はあるか？

会社のOKRや戦略ドキュメントをアップロードとして受け付ける。

### ステップ2：OKRを生成する

**brainstorm-okrs**スキルを適用する：

- 3つのOKRセットを作成する（各Objective + 3〜5つのKey Results）
- **Objectives**：定性的、インスピレーション的、野心的だが達成可能、アクション指向
- **Key Results**：定量的、測定可能、時間制限あり、明確なオーナーを持つ
- OKRが会社の目標に可視的な繋がりで繋がっていることを確認する
- 先行指標（活動）と遅行指標（アウトカム）のバランスを取る

### ステップ3：品質を検証する

ベストプラクティスに照らして各OKRをチェックする：
- ObjectiveはInspiring（鼓舞するもの）か？（チームを結集させられるか？）
- Key Resultsは測定可能か？（判断ではなくデータで完了を確認できるか？）
- 目標は野心的だが落胆させるものではないか？（70%達成 = よく調整されている）
- Objectiveあたり3〜5つのKRがあるか？（それ以上 = 焦点が分散）
- KRはゲーム化を避けているか？（例：「5つの機能をリリースする」はゴミをリリースする動機付けになる）

問題を指摘し改善を提案する。

### ステップ4：提示と反復

```
## Team OKRs: [Team Name] — [Period]

**Aligned to**: [Company Objective(s)]

### Objective 1: [Inspiring qualitative statement]
| # | Key Result | Baseline | Target | Owner |
|---|-----------|----------|--------|-------|
| KR1 | [measurable result] | [current] | [target] | [team/person] |
| KR2 | ... | ... | ... | ... |
| KR3 | ... | ... | ... | ... |

### Objective 2: [Inspiring qualitative statement]
[same format]

### Objective 3: [Inspiring qualitative statement]
[same format]

### Alignment Map
Company Objective → Team Objective → Key Results → Expected Impact

### Scoring Guide
- 0.0-0.3: 大きなミス——調査して学ぶ
- 0.4-0.6: 進捗はあったが目標に届かなかった
- 0.7-0.9: よく調整されたストレッチゴール——これが目標ゾーン
- 1.0: 達成したか、目標が十分に野心的でなかったか

### Check-in Cadence
- **毎週**：各KRに対するトラフィックライト更新
- **四半期中盤**：深いレビュー、コンテキストが変わった場合は目標を調整
- **四半期末**：スコア付け、振り返り、次の四半期に反映
```

以下を提案する：
- 「**野心のレベルを調整**したいですか——より積極的/消極的にしますか？」
- 「これらを追跡するための**メトリクスダッシュボードを作成**しましょうか？」
- 「これらのOKRを紹介する**ステークホルダー向け更新を起草**しましょうか？」

## 注意事項

- OKRはアウトプットではなくアウトカムを説明すべき（「オンボーディングを20%改善する」であって「オンボーディングのリデザインをリリースする」ではない）
- ユーザーが会社のOKRを持っていない場合は、プロダクト戦略やビジネス目標からチームの目標を導き出す手助けをする
- チームあたり四半期に最大3つの目標——それ以上は焦点が薄れる
- Key Resultsはストレッチゴールであるべき——確実に達成できると分かっているなら、十分に野心的ではない
- ゲーム化される可能性があるKRにフラグを立て、カウンター指標を提案する
