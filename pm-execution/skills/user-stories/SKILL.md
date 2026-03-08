---
name: user-stories
description: "3つのC（Card、Conversation、Confirmation）とINVEST基準に従って、説明、デザインリンク、受け入れ基準を含むユーザーストーリーを作成します。ユーザーストーリーの作成、機能をバックログアイテムに分解する、または受け入れ基準の定義に使用します。"
---
# ユーザーストーリー

3つのC（Card、Conversation、Confirmation）とINVEST基準に従ってユーザーストーリーを作成します。説明、デザインリンク、受け入れ基準を含むストーリーを生成します。

**使用する場面：** ユーザーストーリーの作成、機能をストーリーに分解する、バックログアイテムの作成、または受け入れ基準の定義。

**引数：**
- `$PRODUCT`：プロダクトまたはシステム名
- `$FEATURE`：ストーリーに分解する新しい機能
- `$DESIGN`：デザインファイルへのリンク（Figma、Miroなど）
- `$ASSUMPTIONS`：主要な仮定またはコンテキスト

## ステップバイステップのプロセス

1. **機能を分析する**：提供されたデザインとコンテキストに基づいて
2. **ユーザーロールを特定する**：異なるユーザーの旅を特定する
3. **3つのCフレームワークを適用する**：
   - Card：シンプルなタイトルと一行説明
   - Conversation：意図の詳細な議論
   - Confirmation：明確な受け入れ基準
4. **INVEST基準を尊重する**：Independent、Negotiable、Valuable、Estimable、Small、Testable
5. **わかりやすい言葉を使う**：小学生が理解できるレベル
6. **デザインファイルにリンクする**：視覚的な参照のため
7. **ユーザーストーリーを出力する**：構造化されたフォーマットで

## ストーリーテンプレート

**Title:** [機能名]

**Description:** As a [user role], I want to [action], so that [benefit].

**Design:** [デザインファイルへのリンク]

**Acceptance Criteria:**
1. [明確で検証可能な基準]
2. [観察可能な動作]
3. [システムが正しく検証する]
4. [エッジケースの処理]
5. [パフォーマンスまたはアクセシビリティの考慮]
6. [統合ポイント]

## ユーザーストーリーの例

**Title:** Recently Viewed Section

**Description:** As an Online Shopper, I want to see a 'Recently viewed' section on the product page to easily revisit items I considered.

**Design:** [Figmaリンク]

**Acceptance Criteria:**
1. 「最近見た」セクションは、少なくとも1つのプロダクトを以前に見たことがあるすべてのユーザーのプロダクトページ下部に表示される。
2. セッションの最初のプロダクトページを訪問するユーザーには表示されない。
3. 現在のプロダクト自体は表示されるアイテムから除外される。
4. セクションには画像、タイトル、価格を含むプロダクトカードまたはサムネイルが表示される。
5. 各プロダクトカードはいつ見たかを示す（例：「5分前に見た」）。
6. プロダクトカードをクリックすると対応するプロダクトページに移動する。

## 出力成果物

- 機能の完全なユーザーストーリーセット
- 各ストーリーにはタイトル、説明、デザインリンク、4〜6つの受け入れ基準を含む
- ストーリーは独立していてどんな順序でも開発可能
- ストーリーは1スプリントサイクルのサイズ
- ストーリーは関連するデザインドキュメントを参照する

---

### 参考資料

- [How to Write User Stories: The Ultimate Guide](https://www.productcompass.pm/p/how-to-write-user-stories)
