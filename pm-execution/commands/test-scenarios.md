---
description: ユーザーストーリーまたは機能仕様から包括的なテストシナリオを生成する——ハッピーパス、エッジケース、エラーハンドリング
argument-hint: "<user stories, feature spec, or description>"
---

# /test-scenarios -- テストシナリオジェネレーター

ユーザーストーリーまたは機能説明をQAがすぐに実行できる包括的なテストシナリオに変換します。ハッピーパス、エッジケース、エラーハンドリング、クロスブラウザ/デバイスの考慮事項をカバーします。

## 呼び出し方

```
/test-scenarios [paste user stories or acceptance criteria]
/test-scenarios [upload a PRD or feature spec]
/test-scenarios User can reset their password via email link
```

## ワークフロー

### ステップ1：入力を受け取る

以下を受け付ける：ユーザーストーリー、受け入れ基準、PRDセクション、機能説明、または期待される動作のあらゆる仕様。

### ステップ2：テストシナリオを生成する

**test-scenarios**スキルを適用する：

各ユーザーストーリーまたは要件に対して、以下を生成する：

**ハッピーパスシナリオ**：期待されるユーザーフローが正しく機能する
**エッジケース**：境界条件、異常な入力、同時操作
**エラーシナリオ**：問題が発生したときに何が起こるか
**セキュリティシナリオ**：該当する場合（認証、権限、データアクセス）
**パフォーマンスシナリオ**：該当する場合（負荷、タイムアウト、大きなデータ）

### ステップ3：出力を構造化する

```
## Test Scenarios: [Feature]

**Source**: [user stories / PRD / description]
**Total scenarios**: [count]
**Coverage**: [happy path / edge cases / errors / security / performance]

### Scenario 1: [Title]
**Tests**: [どのストーリーまたは要件]
**Preconditions**: [必要なセットアップ]
**User role**: [誰がこれを実行するか]

| Step | Action | Expected Result |
|------|--------|----------------|
| 1 | [user action] | [expected system response] |
| 2 | [user action] | [expected system response] |

**Postconditions**: [完了後の状態]
**Priority**: [Critical / High / Medium / Low]

---
[各シナリオについて繰り返す]

### Coverage Matrix
| Requirement | Happy Path | Edge Cases | Error Handling | Notes |
|------------|-----------|-----------|---------------|-------|

### Test Data Requirements
[これらのシナリオを実行するために必要なテストデータ]
```

markdownとして保存する。

### ステップ4：次のステップを提案する

- 「これらのシナリオ用の**テストデータを生成**したいですか？」
- 「特定のシナリオに**より多くのエッジケースを追加**しましょうか？」
- 「これらのシナリオがテストする**ユーザーストーリーを作成**したいですか？」

## 注意事項

- まずハッピーパスから、次にエッジケースを重ねる——境界をテストする前に基本フローが機能することを確認する
- 元のストーリーからのすべての受け入れ基準は、少なくとも1つのテストシナリオにマッピングされるべき
- ポジティブテスト（機能する）とネガティブテスト（適切に失敗する）の両方を含める
- APIの場合は、レート制限、タイムアウト、不正な形式のリクエスト、認証失敗のシナリオを含める
- 特定のテスト環境またはサードパーティサービスのモッキングが必要なシナリオにフラグを立てる
