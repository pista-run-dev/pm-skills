![GitHub stars](https://img.shields.io/github/stars/phuryn/pm-skills)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)](https://github.com/phuryn/pm-skills/blob/main/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)](https://github.com/phuryn/pm-skills/blob/main/CONTRIBUTING.md)

# PM Skills Marketplace: より良いプロダクト意思決定のためのAIオペレーティングシステム

> 8つのプラグインにまたがる65のPMスキルと36の連鎖ワークフロー。Claude Code、Cowork、その他にも対応。ディスカバリーから戦略、実行、ローンチ、グロースまで。

![Plugin overview](.docs/images/plugins-overview.webp)

Claude CodeとCowork向けに設計されています。スキルは他のAIアシスタントとも互換性があります。

## まず始めに

新しいアイデア？ → `/discover`
戦略的な明確さが必要？ → `/strategy`
PRDを書く？ → `/write-prd`
ローンチを計画する？ → `/plan-launch`
メトリクスを定義する？ → `/north-star`

このプロジェクトが役立ったら、⭐ リポジトリにスターをお願いします。

## なぜPM Skills Marketplaceなのか？

汎用AIはテキストを提供します。PM Skills Marketplaceは構造を提供します。

各スキルには実証済みのPMフレームワーク（ディスカバリー、仮定マッピング、優先順位付け、戦略）が組み込まれており、ステップバイステップでガイドします。Teresa Torres、Marty Cagan、Alberto Savoiaの厳密さが、本棚に飾られるだけでなく、日々のワークフローに組み込まれます。

結果：より速いドキュメントだけでなく、より良いプロダクト意思決定。

## 仕組み（スキル、コマンド、プラグイン）

**スキル**はマーケットプレイスのビルディングブロックです。各スキルはClaudeに特定のPMタスクのためのドメイン知識、分析フレームワーク、またはガイド付きワークフローを提供します。一部のスキルは複数のコマンドが共有する再利用可能な基盤としても機能します。

スキルは会話に関連する場合に自動的に読み込まれます（明示的な呼び出し不要）。必要な場合（例：一般的な知識よりスキルを優先したい場合）、`/plugin-name:skill-name` または `/skill-name`（Claudeがプレフィックスを追加します）で**スキルを強制読み込み**できます。

**コマンド**は `/command-name` で呼び出されるユーザーがトリガーするワークフローです。1つ以上のスキルをエンドツーエンドのプロセスに連鎖させます。例えば、`/discover` は4つのスキルを連鎖させます：brainstorm-ideas → identify-assumptions → prioritize-assumptions → brainstorm-experiments。

**プラグイン**は関連するスキルとコマンドをインストール可能なパッケージにグループ化します。各プラグインはPMドメイン（ディスカバリー、戦略、実行など）をカバーします。マーケットプレイスをインストールすると、8つのプラグイン全てが一度に手に入ります。

![How skills work](.docs/images/how-skills-work.webp)

コマンドはスキルを使用します。一部のスキルは複数のコマンドで機能します。一部のスキル（`prioritization-frameworks` や `opportunity-solution-tree` など）は、コマンドなしにClaudeが適宜参照するスタンドアロンのリファレンスです。

コマンドはPMワークフローに合わせて互いに流れるように設計されています。コマンドが完了した後、関連する次のコマンドが提案されます（プロンプトに従うだけ）。

## インストール

### Claude Cowork（非開発者向け推奨）

1. **カスタマイズ**（左下）を開く
2. **プラグインを参照** → **個人** → **+** に進む
3. **GitHubからマーケットプレイスを追加**を選択
4. `phuryn/pm-skills` を入力

8つのプラグインが全て自動的にインストールされます。コマンド（`/discover`、`/strategy` など）とスキルの両方が使用できます。

![Installing PM Skills in Claude Cowork](.docs/images/pm-skills-install.gif)

### Claude Code（CLI）

```bash
# ステップ1：マーケットプレイスを追加
claude plugin marketplace add phuryn/pm-skills

# ステップ2：個別プラグインをインストール
claude plugin install pm-toolkit@pm-skills
claude plugin install pm-product-strategy@pm-skills
claude plugin install pm-product-discovery@pm-skills
claude plugin install pm-market-research@pm-skills
claude plugin install pm-data-analytics@pm-skills
claude plugin install pm-marketing-growth@pm-skills
claude plugin install pm-go-to-market@pm-skills
claude plugin install pm-execution@pm-skills
```

### 他のAIアシスタント（スキルのみ）

`skills/*/SKILL.md` ファイルはユニバーサルスキル形式に従い、それを読むあらゆるツールで機能します。コマンド（`/スラッシュコマンド`）はClaude専用です。

| ツール | 使用方法 | 動作内容 |
|------|-----------|------------|
| **Gemini CLI** | スキルフォルダを `.gemini/skills/` にコピー | スキルのみ |
| **Cursor** | スキルフォルダを `.cursor/skills/` にコピー | スキルのみ |
| **Codex CLI** | スキルフォルダを `.codex/skills/` にコピー | スキルのみ |
| **Kiro** | スキルフォルダを `.kiro/skills/` にコピー | スキルのみ |

```bash
# 例：Gemini CLI用に全スキルをコピー
for plugin in pm-*/; do
  cp -r "$plugin/skills/"* ~/.gemini/skills/ 2>/dev/null
done
```

---

## 利用可能なプラグイン

<details>
<summary><strong>1. pm-product-discovery</strong> — アイデア出し、実験、仮定テスト、OST、インタビュー（13スキル、5コマンド）</summary>

**スキル（13）：**

- `brainstorm-ideas-existing` — 既存プロダクトのための多角的なアイデア出し（PM、デザイナー、エンジニア）
- `brainstorm-ideas-new` — 初期ディスカバリーにおける新プロダクトのアイデア出し
- `brainstorm-experiments-existing` — 既存プロダクトの仮定をテストするための実験設計
- `brainstorm-experiments-new` — 新プロダクト向けのリーンスタートアップ・プレトタイプ設計（Alberto Savoia）
- `identify-assumptions-existing` — 価値、ユーザビリティ、実行可能性、実現可能性における危険な仮定の特定
- `identify-assumptions-new` — Go-to-Market、戦略、チームを含む8つのリスクカテゴリにわたる危険な仮定の特定
- `prioritize-assumptions` — インパクト×リスクマトリクスを使った仮定の優先順位付けと実験提案
- `prioritize-features` — インパクト、工数、リスク、戦略的整合性に基づくフィーチャーバックログの優先順位付け
- `analyze-feature-requests` — テーマと戦略的適合性によるカスタマーフィーチャーリクエストの分析・分類
- `opportunity-solution-tree` — オポチュニティ・ソリューションツリーの構築（Teresa Torres）— アウトカム → オポチュニティ → ソリューション → 実験
- `interview-script` — JTBDプロービング質問を含む構造化カスタマーインタビュースクリプトの作成
- `summarize-interview` — インタビュー議事録のJTBD、満足シグナル、アクションアイテムへの要約
- `metrics-dashboard` — ノーススター、インプットメトリクス、アラート閾値を含むプロダクトメトリクスダッシュボードの設計

**コマンド（5）：**

- `/discover` — 完全なディスカバリーサイクル：アイデア出し → 仮定マッピング → 優先順位付け → 実験設計
- `/brainstorm` — 多角的アイデア出し（`ideas|experiments` × `existing|new`）
- `/triage-requests` — フィーチャーリクエストのバッチ分析と優先順位付け
- `/interview` — インタビュースクリプトの準備または議事録の要約（`prep|summarize`）
- `/setup-metrics` — プロダクトメトリクスダッシュボードの設計

**使用例：**

スキル：
- `AIライティングアシスタントのアイデアで最もリスクの高い仮定は何ですか？`
- `ユーザーアクティベーション改善のためのOSTを構築してください`
- `エンタープライズ顧客からのこれら12のフィーチャーリクエストを優先順位付けしてください [CSVを添付]`

コマンド：
- `/discover AI搭載のリモートチーム向けミーティングサマライザー`
- `/brainstorm experiments existing — オンボーディングフローのチャーンを削減する必要があります`
- `/interview prep — エンタープライズバイヤーに調達ワークフローについてインタビューします`

</details>

<details>
<summary><strong>2. pm-product-strategy</strong> — ビジョン、ビジネスモデル、価格設定、競合環境（12スキル、5コマンド）</summary>

プロダクト戦略、ビジョン、ビジネスモデル、価格設定、マクロ環境分析。ビジョン構築から競合環境スキャンまでの完全な戦略ツールキットをカバー。

**スキル（12）：**

- `product-strategy` — 包括的な9セクションのプロダクト戦略キャンバス（ビジョン → 防衛可能性）
- `startup-canvas` — プロダクト戦略（9セクション）＋ビジネスモデルを組み合わせたスタートアップキャンバス — 新プロダクト向けBMCとリーンキャンバスの代替
- `product-vision` — 鼓舞的で、達成可能で、感情的なプロダクトビジョンの構築
- `value-proposition` — 6パートJTBDバリュープロポジション（誰が、なぜ、前は何だったか、どのように、後は何か、代替手段）
- `lean-canvas` — スタートアップと新プロダクト向けのリーンキャンバスビジネスモデル
- `business-model` — 9つの構成要素全てを含むビジネスモデルキャンバス
- `monetization-strategy` — 検証実験を含む3〜5つのマネタイズ戦略のブレインストーミング
- `pricing-strategy` — 価格モデル、競合分析、支払意志額、価格弾力性
- `swot-analysis` — 実行可能な推奨事項を含むSWOT分析
- `pestle-analysis` — マクロ環境：政治、経済、社会、技術、法律、環境
- `porters-five-forces` — 競争力分析（競争強度、サプライヤー、バイヤー、代替品、新規参入者）
- `ansoff-matrix` — 市場と製品にわたる成長戦略マッピング

**コマンド（5）：**

- `/strategy` — 包括的な9セクションのプロダクト戦略キャンバスの作成
- `/business-model` — ビジネスモデルの探索（`lean|full|startup|value-prop|all`）
- `/value-proposition` — 6パートJTBDテンプレートを使ったバリュープロポジションの設計
- `/market-scan` — SWOT＋PESTLE＋ポーターの5力＋アンゾフを組み合わせたマクロ環境分析
- `/pricing` — 競合分析と実験を含む価格戦略の設計

**使用例：**

スキル：
- `マーケットプレイス型スタートアップ向けのリーンキャンバス vs ビジネスモデルキャンバス vs スタートアップキャンバスを比較してください`
- `非英語ネイティブを対象とするAIライティングアシスタントのバリュープロポジションを設計してください`
- `プロジェクト管理SaaS市場のポーターの5力分析を実行してください`

コマンド：
- `/strategy エージェンシー向けB2Bプロジェクト管理ツール`
- `/business-model startup — 非英語ネイティブ向けAIライティングツール`
- `/value-proposition エンタープライズ顧客向けSaaSオンボーディングツール`

</details>

<details>
<summary><strong>3. pm-execution</strong> — PRD、OKR、ロードマップ、スプリント、レトロ、リリースノート、ステークホルダー管理（15スキル、10コマンド）</summary>

日々のプロダクト管理：PRD、OKR、ロードマップ、スプリント、レトロスペクティブ、リリースノート、プレモーテム、ステークホルダー管理、ユーザーストーリー、優先順位付けフレームワーク。

**スキル（15）：**

- `create-prd` — 包括的な8セクションのPRDテンプレート
- `brainstorm-okrs` — 会社目標と整合したチームレベルのOKR
- `outcome-roadmap` — フィーチャーリストをアウトカム重視のロードマップに変換
- `sprint-plan` — キャパシティ見積もり、ストーリー選択、リスク特定を含むスプリントプランニング
- `retro` — 構造化されたスプリントレトロスペクティブのファシリテーション
- `release-notes` — チケット、PRD、変更履歴からのユーザー向けリリースノート
- `pre-mortem` — タイガー/ペーパータイガー/エレファント分類によるリスク分析
- `stakeholder-map` — 個別コミュニケーション計画を含むパワー×インタレストグリッド
- `summarize-meeting` — ミーティング議事録 → 決定事項＋アクションアイテム
- `user-stories` — 3つのC（カード、会話、確認）とINVEST基準に従ったユーザーストーリー
- `job-stories` — ジョブストーリー：[状況]の時、[動機]したい、それによって[アウトカム]できるように
- `wwas` — Why-What-Acceptance形式のプロダクトバックログアイテム
- `test-scenarios` — テストシナリオ：ハッピーパス、エッジケース、エラー処理
- `dummy-dataset` — CSV、JSON、SQL、またはPythonとしてのリアルなダミーデータセット
- `prioritization-frameworks` — 9つの優先順位付けフレームワークの参照ガイド（オポチュニティスコア、ICE、RICE、MoSCoW、カノなど）

**コマンド（10）：**

- `/write-prd` — フィーチャーアイデアまたは問題文からPRDを作成
- `/plan-okrs` — チームレベルのOKRのブレインストーミング
- `/transform-roadmap` — フィーチャーベースのロードマップをアウトカム重視に変換
- `/sprint` — スプリントライフサイクル（`plan|retro|release`）
- `/pre-mortem` — PRDまたはローンチ計画のプレモーテムリスク分析
- `/meeting-notes` — ミーティング議事録を構造化ノートに要約
- `/stakeholder-map` — ステークホルダーをマッピングしてコミュニケーション計画を作成
- `/write-stories` — フィーチャーをバックログアイテムに分解（`user|job|wwa`）
- `/test-scenarios` — ユーザーストーリーからテストシナリオを生成
- `/generate-data` — リアルなダミーデータセットを作成

**使用例：**

スキル：
- `50アイテムのバックログにはどの優先順位付けフレームワークを使うべきですか？`
- `プラットフォーム移行プロジェクトのステークホルダーをマッピングしてください`
- `オポチュニティスコア、ICE、RICEの違いは何ですか？`

コマンド：
- `/write-prd アラート疲れを軽減するスマート通知システム`
- `/sprint retro — 前スプリントのノートはこちらです`
- `/write-stories job — 「チームダッシュボード」フィーチャーをジョブストーリーに分解してください`

</details>

<details>
<summary><strong>4. pm-market-research</strong> — ペルソナ、セグメンテーション、ジャーニーマップ、市場規模、競合分析（7スキル、3コマンド）</summary>

ユーザーリサーチと競合分析：ペルソナ、セグメンテーション、ジャーニーマップ、市場規模、競合分析、フィードバック分析。

**スキル（7）：**

- `user-personas` — リサーチデータから洗練されたユーザーペルソナの作成
- `market-segments` — 人口統計、JTBD、プロダクト適合性を含む3〜5つの顧客セグメントの特定
- `user-segmentation` — 行動、JTBD、ニーズに基づくフィードバックデータからのユーザーセグメント化
- `customer-journey-map` — ステージ、タッチポイント、感情、ペインポイントを含むエンドツーエンドのジャーニーマップ
- `market-sizing` — トップダウンとボトムアップアプローチによるTAM、SAM、SOM
- `competitor-analysis` — 競合の強み、弱み、差別化のオポチュニティ
- `sentiment-analysis` — ユーザーフィードバックからのセンチメント分析とテーマ抽出

**コマンド（3）：**

- `/research-users` — ペルソナ構築、ユーザーセグメント化、カスタマージャーニーマッピング
- `/competitive-analysis` — 競合環境の分析
- `/analyze-feedback` — ユーザーフィードバックからのセンチメント分析とセグメントインサイト

**使用例：**

スキル：
- `米国市場のAIコードレビューツールのTAM/SAM/SOMを推定してください`
- `ECサイトのチェックアウトフローのカスタマージャーニーマップを作成してください`
- `これらの調査回答者を行動とニーズでセグメント化してください [CSVを添付]`

コマンド：
- `/research-users フィットネスアプリの12人のユーザーからのインタビューデータがあります`
- `/competitive-analysis デザインツール空間でのFigmaの競合他社`
- `/analyze-feedback Q4からの200件のNPS回答はこちらです [ファイルを添付]`

</details>

<details>
<summary><strong>5. pm-data-analytics</strong> — SQLクエリ生成、コホート分析、A/Bテスト分析（3スキル、3コマンド）</summary>

PM向けデータ分析：SQLクエリ生成、コホート分析、A/Bテスト分析。

**スキル（3）：**

- `sql-queries` — 自然言語からSQL生成（BigQuery、PostgreSQL、MySQL）
- `cohort-analysis` — コホート別の保持率曲線、フィーチャー採用率、エンゲージメントトレンド
- `ab-test-analysis` — 統計的有意性、サンプルサイズ検証、出荷/延長/停止の推奨

**コマンド（3）：**

- `/write-query` — 自然言語からSQLクエリを生成
- `/analyze-cohorts` — ユーザーエンゲージメントデータのコホート分析
- `/analyze-test` — A/Bテスト結果の分析

**使用例：**

スキル：
- `2%のMDEで95%の信頼度を得るには何サンプル必要ですか？`
- `サブスクリプションアプリで追跡すべき保持率メトリクスは何ですか？`

コマンド：
- `/write-query Q4 2025の国別月間アクティブユーザー数を表示（BigQuery）`
- `/analyze-test チェックアウトフローのA/Bテスト結果はこちらです [CSVを添付]`
- `/analyze-cohorts 1月vs2月登録ユーザーの週次保持率`

</details>

<details>
<summary><strong>6. pm-go-to-market</strong> — ビーチヘッドセグメント、ICP、メッセージング、グロースループ、GTMモーション、バトルカード（6スキル、3コマンド）</summary>

Go-to-market戦略：ビーチヘッドセグメント、理想顧客プロファイル、メッセージング、グロースループ、GTMモーション、競合バトルカード。

**スキル（6）：**

- `gtm-strategy` — チャネル、メッセージング、成功メトリクス、ローンチ計画を含む完全なGTM戦略
- `beachhead-segment` — 最初のビーチヘッド市場セグメントの特定
- `ideal-customer-profile` — 人口統計、行動、JTBD、ニーズを含むICP
- `growth-loops` — 持続可能なグロースループ（フライホイール）の設計
- `gtm-motions` — GTMモーションとツールの評価（プロダクトリード、セールスリードなど）
- `competitive-battlecard` — 反論処理と勝利戦略を含む販売準備完了バトルカード

**コマンド（3）：**

- `/plan-launch` — ビーチヘッドからローンチ計画までの完全なGTM戦略
- `/growth-strategy` — グロースループの設計とGTMモーションの評価
- `/battlecard` — 競合バトルカードの作成

**使用例：**

スキル：
- `開発者生産性ツールの最適なビーチヘッドセグメントは何ですか？`
- `フリーミアムティアを持つB2B SaaS向けのグロースループを設計してください`
- `AI搭載HR選考プラットフォームのICPを定義してください`

コマンド：
- `/plan-launch 中規模エンジニアリングチームを対象とするAIコードレビューツール`
- `/battlecard SMB市場向け、当社CRM vs Salesforce`
- `/growth-strategy フリーランサーとスタートアップをつなぐ両面マーケットプレイス`

</details>

<details>
<summary><strong>7. pm-marketing-growth</strong> — マーケティングアイデア、ポジショニング、バリュープロップ、命名、ノーススターメトリクス（5スキル、2コマンド）</summary>

プロダクトマーケティングとグロース：マーケティングアイデア、ポジショニング、バリュープロポジションステートメント、プロダクト命名、ノーススターメトリクス。

**スキル（5）：**

- `marketing-ideas` — チャネルとメッセージングを含むクリエイティブでコスト効率の高いマーケティングアイデア
- `positioning-ideas` — 競合から差別化されたプロダクトポジショニング
- `value-prop-statements` — マーケティング、セールス、オンボーディング向けのバリュープロポジションステートメント
- `product-name` — ブランド価値とオーディエンスに沿ったプロダクト名のブレインストーミング
- `north-star-metric` — ビジネスゲーム分類を含むノーススターメトリクス＋インプットメトリクス

**コマンド（2）：**

- `/market-product` — マーケティングアイデア、ポジショニング、バリュープロップ、プロダクト名のブレインストーミング
- `/north-star` — ノーススターメトリクスとサポートするインプットメトリクスの定義

**使用例：**

スキル：
- `Notionから差別化する5つのポジショニング角度をブレインストーミングしてください`
- `両面マーケットプレイスの良いノーススターメトリクスは何ですか？`
- `セールスチームのピッチデッキ用のバリュープロップステートメントを生成してください`

コマンド：
- `/market-product ECマネージャー向けB2B分析ダッシュボード`
- `/north-star フリーランサーとクライアントをつなぐ両面マーケットプレイス`

</details>

<details>
<summary><strong>8. pm-toolkit</strong> — 履歴書レビュー、法的文書、校正（4スキル、5コマンド）</summary>

コアなプロダクト業務を超えたPMユーティリティ：履歴書レビュー、法的文書、校正。

**スキル（4）：**

- `review-resume` — 10のベストプラクティスに対するPM履歴書レビューとカスタマイズ（XYZ+S公式、キーワード、構造）
- `draft-nda` — 管轄に適した条項を含む秘密保持契約書
- `privacy-policy` — GDPR/CCPAコンプライアンスをカバーするプライバシーポリシー
- `grammar-check` — 文法、論理、フローのチェックと的を絞った修正

**コマンド（5）：**

- `/review-resume` — 包括的なPM履歴書レビュー
- `/tailor-resume` — 特定の求人説明に合わせた履歴書のカスタマイズ
- `/draft-nda` — NDAの草案作成
- `/privacy-policy` — プライバシーポリシーの草案作成
- `/proofread` — 文法、論理、フローのチェック

**使用例：**

スキル：
- `ベストプラクティスに対してPM履歴書をレビューしてください [PDFを添付]`
- `このプロダクト発表の文法と明瞭さをチェックしてください`

コマンド：
- `/review-resume [PM履歴書を添付]`
- `/tailor-resume [履歴書＋求人説明を添付]`
- `/proofread Q1投資家アップデートの草案はこちらです`

</details>

---

## について

このマーケットプレイスはプロダクト実践とAI能力とともに進化します。

以下の方々の業績に基づいて選定されたスキル：

- Teresa Torres — [*Continuous Discovery Habits*](https://www.amazon.com/Continuous-Discovery-Habits-Discover-Products/dp/1736633309/)
- Marty Cagan — [*INSPIRED*](https://www.amazon.com/INSPIRED-Create-Tech-Products-Customers/dp/1119387507/) および [*TRANSFORMED*](https://www.amazon.com/dp/1119697336/)
- Alberto Savoia — [*The Right It*](https://www.amazon.com/Right-Many-Ideas-Yours-Succeed/dp/0062884654)
- Dan Olsen — [*The Lean Product Playbook*](https://www.amazon.com/dp/1118960874/)
- Roger L. Martin — [*Playing to Win*](https://www.amazon.com/Playing-Win-Expanded-Bonus-Articles/dp/B0F25SDYWV/)
- Ash Maurya — [*Running Lean*](https://www.amazon.com/dp/B004J4XGN6/)
- Strategyzer — [*Business Model Generation*](https://www.amazon.com/dp/0470876417/) および [*Value Proposition Design*](https://www.amazon.com/dp/1118968050/)
- Christina Wodtke — [*Radical Focus*](https://www.amazon.com/Radical-Focus-Achieving-Important-Objectives/dp/0996006052)
- Anthony W. Ulwick — [*Jobs to Be Done*](https://jobs-to-be-done-book.com/)
- Alistair Croll & Benjamin Yoskovitz — [*Lean Analytics*](https://www.amazon.com/Lean-Analytics-Better-Startup-Faster/dp/1449335675/)
- Sean Ellis — [*Hacking Growth*](https://www.amazon.com/Hacking-Growth-Fastest-Growing-Companies-Breakout/dp/045149721X/)
- Maja Voje — [*Go-To-Market Strategist*](https://gtmstrategist.com/)

[The Product Compass Newsletter](https://www.productcompass.pm) のPaweł Hurynが厳選。

## コントリビューション

[CONTRIBUTING.md](CONTRIBUTING.md) を参照してください。

## Windowsでの既知の問題

CoworkがVMを起動できずに不安定な場合（[claude-code/issues/27010](https://github.com/anthropics/claude-code/issues/27010)）は、次を試してください：

```powershell
$action = New-ScheduledTaskAction -Execute "powershell.exe" -Argument "-WindowStyle Hidden -Command `"if ((Get-Service CoworkVMService).Status -ne 'Running') { Start-Service CoworkVMService }`""

$trigger = New-ScheduledTaskTrigger -RepetitionInterval (New-TimeSpan -Minutes 1) -Once -At (Get-Date)

$settings = New-ScheduledTaskSettingsSet -AllowStartIfOnBatteries -DontStopIfGoingOnBatteries

Register-ScheduledTask -TaskName "CoworkVMServiceMonitor" `
  -Action $action `
  -Trigger $trigger `
  -Settings $settings `
  -RunLevel Highest `
  -User "SYSTEM"
```

Windowsの問題の90%が解決されます。
残りの10%：services.mscを開いて「Claude」サービスを手動で起動してください。

## ライセンス

MIT — [LICENSE](LICENSE) を参照してください。
