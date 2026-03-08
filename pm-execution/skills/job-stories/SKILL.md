---
name: job-stories
description: "「When [situation], I want to [motivation], so I can [outcome]」フォーマットを使用して、詳細な受け入れ基準を含むジョブストーリーを作成します。ジョブストーリーの作成、JTBDスタイルのバックログアイテムの作成、またはユーザーの状況と動機の表現に使用します。"
---
# ジョブストーリー

「When [situation], I want to [motivation], so I can [outcome]」フォーマットを使用してジョブストーリーを作成します。ユーザーの状況とアウトカムに焦点を当てた詳細な受け入れ基準を含むストーリーを生成します。

**使用する場面：** ジョブストーリーの作成、ユーザーの状況と動機の表現、JTBDスタイルのバックログアイテムの作成、またはユーザーロールではなくユーザーコンテキストへの焦点。

**引数：**
- `$PRODUCT`：プロダクトまたはシステム名
- `$FEATURE`：ジョブストーリーに分解する新しい機能
- `$DESIGN`：デザインファイルへのリンク（Figma、Miroなど）
- `$CONTEXT`：ユーザーの状況またはジョブシナリオ

## ステップバイステップのプロセス

1. **ユーザーの状況を特定する**：ニーズを引き起こすトリガー
2. **動機を定義する**：ユーザーの行動の根底にある動機
3. **アウトカムを明確にする**：ユーザーが達成したいこと
4. **JTBDフレームワークを適用する**：ロールではなくジョブに焦点を当てる
5. **受け入れ基準を作成する**：アウトカムが達成されたことを検証する
6. **観察可能で測定可能な言語を使用する**
7. **デザインモックアップまたはプロトタイプにリンクする**
8. **ジョブストーリーを出力する**：詳細な受け入れ基準と共に

## ストーリーテンプレート

**Title:** [ジョブのアウトカムまたは結果]

**Description:** When [situation], I want to [motivation], so I can [outcome].

**Design:** [デザインファイルへのリンク]

**Acceptance Criteria:**
1. [状況が適切に認識される]
2. [システムが望ましい動機を可能にする]
3. [進捗またはフィードバックが見える]
4. [アウトカムが効率的に達成される]
5. [エッジケースが適切に処理される]
6. [統合と通知が機能する]

## ジョブストーリーの例

**Title:** Track Weekly Snack Spending

**Description:** When I'm preparing my weekly allowance for snacks (situation), I want to quickly see how much I've spent so far (motivation), so I can make sure I don't run out of money before the weekend (outcome).

**Design:** [Figmaリンク]

**Acceptance Criteria:**
1. 「Weekly Spending Overview」セクションで支出サマリーを表示する
2. 経費が記録されたときにリアルタイム更新する
3. 週間予算の0〜100%を示すプログレスバー（進捗インジケーター）
4. 目立つ色で残りの予算をハイライトする
5. カテゴリ別の内訳を含む詳細な支出ログ
6. 予算の80%時に通知する
7. 木曜日の夜の90%時に週末固有のリマインダー
8. 詳細な内訳への簡単なアクセスとナビゲーション

## 出力成果物

- 機能の完全なジョブストーリーセット
- 各ストーリーは「When...I want...so I can」フォーマットに従う
- アウトカムに焦点を当てた6〜8つの受け入れ基準
- ストーリーはユーザーの状況と動機を強調する
- デザインとプロトタイプへの明確なリンク

---

### 参考資料

- [Jobs-to-be-Done Masterclass with Tony Ulwick and Sabeen Sattar](https://www.productcompass.pm/p/jobs-to-be-done-masterclass-with)（動画コース）
