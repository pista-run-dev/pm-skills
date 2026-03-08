---
description: 機能をバックログアイテムに分解する——受け入れ基準を含むユーザーストーリー、ジョブストーリー、またはWWAフォーマット
argument-hint: "[user|job|wwa] <feature description or PRD>"
---

# /write-stories -- バックログアイテムジェネレーター

機能を構造化されたバックログアイテムに分解します。チームの好みに応じて3つのフォーマットから選択でき、各フォーマットには完全な受け入れ基準が含まれます。

## 呼び出し方

```
/write-stories user Allow users to export reports as PDF and CSV
/write-stories job Notification system for task deadlines
/write-stories wwa Dark mode for the mobile app
/write-stories [upload a PRD or feature spec]      # フォーマットの好みを質問する
/write-stories                                      # 機能とフォーマットを質問する
```

## フォーマット

### ユーザーストーリー
**フォーマット**：「As a [user type], I want [capability], so that [benefit]」
**user-stories**スキルを適用する：
- 3つのCに従う：Card（簡潔）、Conversation（コンテキスト）、Confirmation（受け入れ基準）
- INVESTに対して検証する：Independent、Negotiable、Valuable、Estimable、Small、Testable
- 関連する場合はデザインリンクまたはモックアップ参照を含める

### ジョブストーリー
**フォーマット**：「When [situation], I want to [motivation], so I can [outcome]」
**job-stories**スキルを適用する：
- ユーザーロールではなく、状況とコンテキストに焦点を当てる
- 調査で観察された実際のユーザーシナリオに基づく
- JTBDに特化したチームに最適

### WWA (Why-What-Acceptance)
**フォーマット**：Why [戦略的コンテキスト] → What [成果物] → Acceptance [基準]
**wwas**スキルを適用する：
- 戦略的な根拠を含める（なぜこれを構築するのか）
- 独立した、価値ある、検証可能なアイテムを生成する
- ビジネスコンテキストが必要なクロスファンクショナルチームに適している

## ワークフロー

### ステップ1：機能を受け取る

以下の形式で受け付ける：PRD、機能説明、ユーザー調査の発見、または口頭によるアイデア。PRDが提供された場合は、要件を抽出して分解する。

### ステップ2：フォーマットを決定する

呼び出しで指定されていない場合は、以下を質問する：
- 「チームはどのフォーマットを使っていますか？**ユーザーストーリー**、**ジョブストーリー**、または**WWA**？」
- 不明な場合は、デフォルトとしてユーザーストーリーを推奨する

### ステップ3：機能を分解する

- 機能を5〜15の独立したストーリーに分解する（1スプリントで完了できるほど小さい）
- 各ストーリーが独立して価値があることを確認する（単独でユーザー価値を提供する）
- 依存関係と優先度で順序付ける
- ストーリーごとに3〜5つの受け入れ基準を書く
- デザイン入力または技術的スパイクが必要なストーリーにフラグを立てる

### ステップ4：ストーリーを生成する

```
## Backlog: [Feature Name]

**Format**: [User Stories / Job Stories / WWA]
**Total stories**: [count]
**Estimated total effort**: [if possible]

### Stories

#### Story 1: [Short title]
**[The story in chosen format]**

Acceptance Criteria:
- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion 3]

Priority: [P0/P1/P2] | Effort: [S/M/L] | Dependencies: [none or list]

---
[Repeat for each story]

### Story Map
[視覚的な順序付け：must-have → should-have → nice-to-have]

### Technical Notes
[横断的な懸念：API変更、データ移行、インフラ]

### Open Questions
[実装を開始する前に答えが必要なこと]
```

markdownとして保存する。

### ステップ5：次のステップを提案する

- 「これらのストーリーの**テストシナリオを生成**したいですか？」
- 「開発とテスト用の**ダミーデータを作成**しましょうか？」
- 「これらのストーリーの**スプリントキャパシティを推定**したいですか？」
- 「**別のフォーマットに変換**したいですか（ユーザーストーリー ↔ ジョブストーリー ↔ WWA）？」

## 注意事項

- 1つのストーリー = デプロイ可能な1つの価値単位——別のストーリーがないと役に立たない場合は、組み合わせるべき
- 受け入れ基準は追加の解釈なしにQAが検証可能であるべき
- エラーハンドリングとエッジケースは、ハッピーパスのストーリーの箇条書きではなく、独自のストーリーに値する
- 機能が大きい場合（15以上のストーリー）は、エピックまたはフェーズにグループ化することを提案する
- 推定が可能になる前に技術的調査が必要なストーリーにフラグを立てる
