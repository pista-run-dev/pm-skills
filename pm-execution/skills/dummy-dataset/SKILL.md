---
name: dummy-dataset
description: "カスタマイズ可能なカラム、制約、出力フォーマット（CSV、JSON、SQL、Pythonスクリプト）を持つテスト用のリアルなダミーデータセットを生成します。テストデータの作成、モックデータセットの構築、または開発とデモ用のサンプルデータの生成に使用します。"
---
# ダミーデータセット生成

カスタマイズ可能なカラム、制約、出力フォーマット（CSV、JSON、SQL、Pythonスクリプト）を持つテスト用のリアルなダミーデータセットを生成します。即時使用のための実行可能なスクリプトまたは直接データファイルを作成します。

**使用する場面：** テストデータの作成、サンプルデータセットの生成、開発用のリアルなモックデータの構築、またはテスト環境のデータ投入。

**引数：**
- `$PRODUCT`：プロダクトまたはシステム名
- `$DATASET_TYPE`：データのタイプ（例：顧客フィードバック、トランザクション、ユーザープロフィール）
- `$ROWS`：生成する行数（デフォルト：100）
- `$COLUMNS`：含める特定のカラムまたはフィールド
- `$FORMAT`：出力フォーマット（CSV、JSON、SQL、Pythonスクリプト）
- `$CONSTRAINTS`：追加の制約またはビジネスルール

## ステップバイステップのプロセス

1. **データセットタイプを特定する** - データドメインを理解する
2. **カラム仕様を定義する** - 名前、データタイプ、値の範囲
3. **行数を決定する** - 必要なサンプルレコード数
4. **出力フォーマットを選択する** - CSV、JSON、SQL INSERT、またはPythonスクリプト
5. **リアルなパターンを適用する** - データが本物らしく有効に見えることを確保する
6. **ビジネス制約を追加する** - ビジネスロジックと関係を尊重する
7. **データを生成またはスクリプト化する** - 実行可能な出力を作成する
8. **出力を検証する** - データの品質と完全性を確保する

## テンプレート：Pythonスクリプト出力

```python
import csv
import json
from datetime import datetime, timedelta
import random

# Configuration
ROWS = $ROWS
FILENAME = "$DATASET_TYPE.csv"

# Column definitions with realistic value generators
columns = {
    "id": "auto-increment",
    "name": "first_last_name",
    "email": "email",
    "created_at": "timestamp",
    # Add more columns...
}

def generate_dataset():
    """Generate realistic dummy dataset"""
    data = []
    for i in range(1, ROWS + 1):
        record = {
            "id": f"U{i:06d}",
            # Generate values based on column definitions
        }
        data.append(record)
    return data

def save_as_csv(data, filename):
    """Save dataset as CSV"""
    with open(filename, 'w', newline='') as f:
        writer = csv.DictWriter(f, fieldnames=data[0].keys())
        writer.writeheader()
        writer.writerows(data)

if __name__ == "__main__":
    dataset = generate_dataset()
    save_as_csv(dataset, FILENAME)
    print(f"Generated {len(dataset)} records in {FILENAME}")
```

## データセット仕様の例

**データセットタイプ：** 顧客フィードバック

**カラム：**
- feedback_id（自動増分、U001、U002...）
- customer_name（リアルな名前）
- email（有効なメール形式）
- feedback_date（過去90日間の日付）
- rating（1〜5つ星）
- category（Bug、Feature Request、Complaint、Praise）
- text（リアルなフィードバック）
- product（electronics、clothing、home）

**制約：**
- 評価の偏り：5つ星40%、4つ星30%、3つ星20%、1〜2つ星10%
- Bugカテゴリは評価1〜3のみ
- Feature requestsは評価3〜5のみ
- メールドメインはリアル（gmail、yahoo、company.com）

## 出力成果物

- すぐに実行できるPythonスクリプトまたは直接データファイル
- 適切なヘッダーとフォーマットを持つCSVファイル
- 有効な構造とタイプを持つJSONファイル
- データベース投入のためのSQL INSERTステートメント
- データ検証と制約コンプライアンス
- リアルでビジネスに適した値
- データ生成ロジックのドキュメント
- データセット使用のためのクイックスタート手順

## 出力フォーマット

**CSV：** フラットな表形式、スプレッドシートとデータベースへのインポートが簡単

**JSON：** ネスト構造、APIとNoSQLデータベースに最適

**SQL：** INSERTステートメント、リレーショナルデータベースで直接実行可能

**Python Script：** カスタムまたは大規模データセットのための実行可能なジェネレーター
