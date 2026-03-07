# CTE

| 項目 | 値 |
|------|---|
| 理解度 | [x][x][ ][ ] |
| 保存日 | 2026-02-25 |
| 最終復習 | 2026-03-03 |
| 次回復習 | 2026-03-06 |

**Q:** CTEとは何か？名前のないサブクエリとの違いは？

**A:** `WITH 名前 AS (サブクエリ)` の形で書く**名前付き**サブクエリ。CTEは必ず名前を持ち、そのクエリ内でのみ有効なスコープを持ち、後続の `SELECT` から複数回参照できる。名前のないインラインのサブクエリは「派生テーブル」「インラインビュー」と呼ばれ、CTEとは区別される。

**メモ:** "Common Table Expression" の "Table Expression" が「名前を付けてテーブルのように扱える」という意味を含む。ページネーションでの CTE方式とウィンドウ関数方式の比較は [[ウィンドウ関数-ページネーション最適化]] を参照。使うときは「CTEを定義/宣言する」が自然な表現（「設定する」より）。複雑なサブクエリを上から順に分解して可読性を上げるのが主な用途。

名前のないサブクエリ（派生テーブル）は `FROM (SELECT ...) AS t` のように FROM の中にネストして書く。CTE はそれをフラットに切り出したもの：

```sql
-- 派生テーブル（ネスト）
SELECT * FROM (SELECT id, name FROM users WHERE active = true) AS active_users

-- CTE（フラット）
WITH active_users AS (SELECT id, name FROM users WHERE active = true)
SELECT * FROM active_users
```
