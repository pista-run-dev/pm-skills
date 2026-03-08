---
description: A/Bテスト結果を分析する — 統計的有意性、サンプルサイズの検証、リリース/延長/停止の推奨
argument-hint: "<データ、スクリーンショット、または説明としてのテスト結果>"
---

# /analyze-test -- A/B Test Analysis

統計的な厳密さで実験結果を評価し、明確なプロダクト意思決定に変換します：リリース、延長、または停止。

## 呼び出し方

```
/analyze-test Control: 4.2% conversion (n=5000), Variant: 4.8% conversion (n=5100)
/analyze-test [テスト結果のCSVをアップロード]
/analyze-test [実験プラットフォームのスクリーンショット]
```

## ワークフロー

### ステップ1: テストデータを受け付ける

任意の形式で受け付けます：
- サマリー統計（コンバージョン率、バリアントごとのサンプルサイズ）
- 生イベントデータ（user_id、variant、converted、timestamp を含むCSV）
- 実験プラットフォームのスクリーンショット（Optimizely、LaunchDarklyなど）
- 実験と結果の説明

### ステップ2: テスト設計を検証する

結果を分析する前に確認します：
- サンプルサイズは十分だったか？（検出力分析を実行する）
- テストは十分な期間実行されたか？（週次サイクルを捉える、最低1〜2ビジネスサイクル）
- ランダム化はきれいだったか？（サンプル比率不一致を確認する）
- テスト期間中に外部要因はあったか？

問題が見つかった場合はフラグを立てる — 欠陥のあるテストの結果は誤解を招く可能性があります。

### ステップ3: 結果を分析する

**ab-test-analysis** スキルを適用します：

- **統計的有意性**: p値と信頼区間を計算する
- **効果サイズ**: バリアント間の絶対的および相対的な差異
- **実務的有意性**: 効果はビジネスにとって十分に大きいか？
- **信頼区間**: 真の効果の妥当な範囲は何か？
- **セグメント分析**: データが許す場合、ユーザーセグメントごとの差分効果を確認する

### ステップ4: 分析を生成する

```
## A/B Test Analysis: [テスト名]

**Date**: [today]
**Test duration**: [X days/weeks]
**Total sample**: [N users]

### Results Summary
| Variant | Sample | Metric | Rate | 95% CI |
|---------|--------|--------|------|--------|
| Control | [n] | [metric] | [X%] | [X% - Y%] |
| Variant | [n] | [metric] | [X%] | [X% - Y%] |

### Statistical Analysis
- **Relative lift**: [+X%] ([CI range])
- **P-value**: [X]
- **Statistically significant**: [Yes/No] at 95% confidence
- **Minimum detectable effect**: [X%] (テストが検出する効果)

### Sample Size Check
- **Required sample**: [N] per variant (for [X%] MDE at 80% power)
- **Actual sample**: [N] per variant
- **Verdict**: [Sufficiently powered / Underpowered / Overpowered]

### Decision

**Recommendation: [SHIP / EXTEND / STOP]**

[統計的有意性と実務的有意性の両方を考慮した明確な理由]

### Business Impact Estimate
100%のユーザーにリリースした場合：
- **Expected impact**: [月次/四半期ごとの指標変化]
- **Revenue impact**: [該当する場合]
- **Confidence**: [この推定値の確実性]

### Caveats
- [テストの妥当性に関する懸念]
- [結果が異なるセグメント]
- [考慮すべきノベルティ効果またはその他のバイアス]

### Follow-Up
- [学習に基づいて次にテストすること]
- [バリアントをリリースする場合のモニタリング計画]
```

### ステップ5: 次のステップを提案する

- 「これらの発見に基づいて**フォローアップ実験を設計**しましょうか？」
- 「**特定のセグメントの分析を実行**すべきでしょうか？」
- 「ローンチ後にこの指標をモニタリングするための**SQLを生成**しましょうか？」

## 注意事項

- 統計的有意性 ≠ 実務的有意性 — 0.1%のリフトは十分なデータで有意になり得るが、リリースする価値はないかもしれない
- 結果を信頼する前に必ずサンプル比率不一致を確認する
- ノベルティ効果は短期的な結果を膨らませる可能性がある — ローンチ後2〜4週間モニタリングすることを推奨する
- テストがアンダーパワーの場合、正しい答えは通常「効果なし」ではなく「延長する」
- 収益指標には、信頼区間を使用してベストケースとワーストケースのビジネスインパクトを推定する
- データがCSVとして提供された場合は、scipy.stats を使用したPythonで完全な分析を生成する
