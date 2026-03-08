---
description: スプリントライフサイクル——スプリントの計画、レトロスペクティブの実施、またはリリースノートの生成
argument-hint: "[plan|retro|release-notes] <context>"
---

# /sprint -- スプリントライフサイクル

スプリントライフサイクルをカバーする3つのモード：スプリント計画のための**plan**、レトロスペクティブのための**retro**、リリースコミュニケーションのための**release-notes**。

## 呼び出し方

```
/sprint plan 2-week sprint, 4 engineers, focus on checkout improvements
/sprint retro [paste team feedback or sprint data]
/sprint release-notes [paste tickets, changelog, or PRD]
/sprint                    # どのフェーズにいるか質問する
```

## モード

---

### Planモード

キャパシティ推定、ストーリー選択、リスク特定でスプリント計画を準備する。

#### ワークフロー

**ステップ1：スプリントコンテキストを収集する**
- スプリント期間（1週間または2週間）
- チーム構成（エンジニア、デザイナー、QA——と可用性）
- スプリントゴールまたは集中エリア
- 検討するバックログアイテム（貼り付け、アップロード、または説明）
- 前のスプリントからのキャリーオーバー
- 既知の中断（祝日、オンコール、ミーティング）

**ステップ2：キャパシティを推定する**

**sprint-plan**スキルを適用する：

- ミーティング、オンコール、PTO後の利用可能なエンジニアリング時間/ポイントを計算する
- 過去のデータ（提供された場合）または業界標準（理論上のキャパシティの70%）に基づいてベロシティ調整を適用する
- チームメンバーごとのキャパシティ内訳を表示する

**ステップ3：ストーリーを選択して順序付けする**

- キャパシティ内に収まるストーリーを推奨する
- 依存関係チェーンをフラグに立てる（AはBが始まる前に完了する必要がある）
- リスクを特定する：仕様が不十分、外部依存関係がある、デザイン入力が必要なストーリー
- クイックウィンと大きなアイテムのバランスを取る
- すべてのストーリーが受け入れ基準を持っていることを確認する

**ステップ4：スプリント計画を生成する**

```
## Sprint Plan: [Sprint Name/Number]

**Duration**: [dates]
**Sprint Goal**: [one sentence]
**Team**: [members and availability]

### Capacity
| Member | Available Days | Points/Hours | Notes |
|--------|--------------|-------------|-------|

**Total capacity**: [X] points/hours
**Recommended commitment**: [Y] points/hours (with buffer)

### Selected Stories
| # | Story | Points | Owner | Dependencies | Risk |
|---|-------|--------|-------|-------------|------|

### Sprint Risks
1. [Risk] — Mitigation: [action]

### Definition of Done
- [ ] Code reviewed
- [ ] Tests passing
- [ ] Deployed to staging
- [ ] QA approved
- [ ] Documentation updated (if applicable)
```

---

### Retroモード

実行可能な改善を生み出す構造化されたレトロスペクティブを進行する。

#### ワークフロー

**ステップ1：スプリントフィードバックを収集する**

以下の形式で入力を受け付ける：
- チームフィードバック（アンケート、Slack、または共同ドキュメントから貼り付け）
- スプリント指標（ベロシティ、バグ、インシデント）
- ユーザー自身の観察

質問する：「どのレトロフォーマットを好みますか？」
- **Start/Stop/Continue**（シンプル、高速）
- **4Ls**（Liked、Learned、Lacked、Longed for）
- **Sailboat**（Wind = 助け、Anchor = 遅らせる、Rocks = リスク、Island = 目標）

**ステップ2：分析と構造化**

**retro**スキルを適用する：

- フィードバックを選択したフレームワークに分類する
- テーマとパターンを特定する
- 症状と根本原因を分離する
- 称賛すべき勝利をハイライトする

**ステップ3：レトロサマリーを生成する**

```
## Sprint Retrospective: [Sprint Name]

**Date**: [today]
**Format**: [Start/Stop/Continue | 4Ls | Sailboat]
**Participants**: [if known]

### What Went Well
[裏付けとなる証拠を含むグループ化されたテーマ]

### What Didn't Go Well
[根本原因分析を含むグループ化されたテーマ]

### Key Insights
[浮かび上がった2〜3つのパターン]

### Action Items
| # | Action | Owner | Deadline | Priority |
|---|--------|-------|----------|----------|

### Metrics This Sprint
| Metric | This Sprint | Last Sprint | Trend |
|--------|-----------|------------|-------|
```

---

### Release Notesモード

技術的な成果物からユーザー向けリリースノートを生成する。

#### ワークフロー

**ステップ1：リリースコンテンツを受け取る**

以下を受け付ける：
- Jira/Linearチケットまたは変更履歴
- PRDまたは機能仕様
- Gitコミットメッセージまたはプルリクエストの説明
- チームのリリース内容の内部サマリー

**ステップ2：変換する**

**release-notes**スキルを適用する：

- 技術的な言語をユーザーへのメリットに翻訳する
- 新機能、改善点、バグ修正として分類する
- プロダクトの声で書く（不明な場合はトーンについて質問する）
- 最も影響の大きい変更を最初にハイライトする

**ステップ3：リリースノートを生成する**

```
## What's New — [Version/Date]

### Highlights
[最も重要な変更の1〜2文のサマリー]

### New Features
- **[Feature Name]** — [わかりやすい言葉でのユーザー向けメリット]

### Improvements
- **[Improvement]** — [今より良くなったこと]

### Bug Fixes
- Fixed [issue] that caused [user impact]

### Coming Soon
[次のリリースのオプションのティーザー]
```

markdownとして保存し、異なるチャンネル（ブログポスト、アプリ内、メール、Slackアナウンスメント）向けにフォーマットを変換する提案をする。

## 注意事項

- planモードの場合：予定外の作業のために20%のバッファを確保する——100%のキャパシティで計画するチームは常に目標を逃す
- retroモードの場合：10の事項ではなく2〜3の影響の大きいアクションアイテムに集中する
- release notesの場合：常に変更をユーザーへのメリットとして表現し、技術的な実装としては表現しない
- 各モードは他のモードに連鎖できる：plan → （スプリント実施）→ retro → release-notes
