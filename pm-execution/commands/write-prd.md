---
description: 機能のアイデアや問題ステートメントから包括的なプロダクト要件ドキュメントを作成する
argument-hint: "<feature or problem statement>"
---

# /write-prd -- プロダクト要件ドキュメント

ステークホルダーを整合させ、開発を導く構造化されたPRDを作成します。漠然としたアイデアから詳細なブリーフまで、あらゆる入力を受け付けます。

## 呼び出し方

```
/write-prd SSO support for enterprise customers
/write-prd Users are dropping off during onboarding — we need to fix step 3
/write-prd [upload a brief, research doc, or strategy deck]
```

## ワークフロー

### ステップ1：機能を理解する

以下の形式で入力を受け付けます：
- 機能名（「SSO support」）
- 問題ステートメント（「Enterprise customers keep asking for centralized auth」）
- ユーザーリクエスト（「Users want to export their data as CSV」）
- 漠然としたアイデア（「We should do something about onboarding drop-off」）
- アップロードされたドキュメント（ブリーフ、調査、Slackスレッド、メール）

### ステップ2：コンテキストを収集する

会話形式で質問する——最も重要な質問から始め、進めながらギャップを埋める：

1. **ユーザーの問題**：どんな問題を解決するか？誰が経験しているか？どれくらい苦痛か？
2. **ターゲットユーザー**：どのユーザーセグメント？何人？現在の回避策は？
3. **成功指標**：これが機能したとどうやって知るか？うまくいった場合に何が動くか？
4. **制約**：技術的制約、タイムライン、規制、他チームへの依存？
5. **先行例**：以前に試みられたか？市場の既存ソリューションは？
6. **スコープの好み**：完全なソリューションか段階的アプローチか？

ユーザーがコンテキストを含むドキュメントを提供した場合は、利用可能な情報を抽出し、ギャップのみについて質問する。

### ステップ3：PRDを生成する

**create-prd**スキルを適用して8セクションのドキュメントを生成する：

```
## Product Requirements Document: [Feature Name]

**Author**: [user]
**Date**: [today]
**Status**: Draft
**Stakeholders**: [if known]

### 1. Executive Summary
[2-3 sentences: what, for whom, why now]

### 2. Background & Context
[Problem space, prior research, market context, what prompted this]

### 3. Objectives & Success Metrics
**Goals** (what success looks like):
1. [Specific, measurable goal]
2. [...]

**Non-Goals** (explicitly out of scope):
1. [What we're not doing, and why]
2. [...]

**Success Metrics**:
| Metric | Current | Target | Measurement |
|--------|---------|--------|-------------|

### 4. Target Users & Segments
[Who this serves, user profiles, segment sizing]

### 5. User Stories & Requirements

**P0 — Must Have**:
| # | User Story | Acceptance Criteria |
|---|-----------|-------------------|

**P1 — Should Have**:
| # | User Story | Acceptance Criteria |
|---|-----------|-------------------|

**P2 — Nice to Have / Future**:
| # | User Story | Acceptance Criteria |
|---|-----------|-------------------|

### 6. Solution Overview
[High-level approach, key design decisions, technical approach if known]

### 7. Open Questions
| Question | Owner | Deadline |
|----------|-------|----------|

### 8. Timeline & Phasing
[Milestones, dependencies, phasing if applicable]
```

### ステップ4：レビューと反復

生成後、以下を提案する：
- 「**スコープを絞り込み**たいですか？P1の中でP2にすべきものを検討できます。」
- 「このPRDに対して**プレモーテムを実施**しましょうか？」
- 「エンジニアリング向けに**ユーザーストーリーに分解**しましょうか？」
- 「これを広めるための**ステークホルダー向け更新**を作成しましょうか？」

PRDをユーザーのワークスペースのmarkdownファイルとして保存する。

## 注意事項

- スコープについて意見を持つ——コンパクトなPRDは広範で曖昧なものより優れている
- アイデアが大きすぎる場合は、積極的に段階化を提案してフェーズ1のみを仕様化する
- Non-goalsはgoalsと同じくらい重要——スコープクリープを防ぐ
- 成功指標は具体的でなければならない：「NPSを改善する」は不良、「ローンチから90日以内にNPSを32から45に増加させる」は良好
- 未解決の質問はコンテキストから答えられるものをリストに入れない
- ユーザーが調査を提供した場合は、帰属を示してBackgroundセクションにインサイトを組み込む
