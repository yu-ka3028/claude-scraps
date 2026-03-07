# ウィンドウ関数-OVER句

| 項目 | 値 |
|------|---|
| 理解度 | [x][x][x][ ] |
| 保存日 | 2026-03-01 |
| 最終復習 | 2026-03-04 |
| 次回復習 | 2026-03-11 |

**Q:** ウィンドウ関数で `OVER` を使う意味は？通常の集約関数と何が違うか？

**A:** `OVER` は「どの行の範囲（ウィンドウ）に対して集計するか」を定義するキーワード。通常の集約関数は複数行を1行に潰すが、`OVER` を付けると行を潰さず各行に集計値を貼り付ける。

```sql
-- GROUP BY → 潰す（行数が減る）
SELECT category, COUNT(*) FROM orders GROUP BY category
-- A | 2
-- B | 1

-- OVER() → 潰さない（元の行が残る）
SELECT id, category, COUNT(*) OVER() FROM orders
-- 1 | A | 3
-- 2 | A | 3
-- 3 | B | 3
```

**メモ:** `OVER()` の中が空 = 全行をウィンドウとする。`PARTITION BY` で絞ると「同じグループ内の行」が対象になる。名前の由来は "calculate COUNT **over** this window of rows"（この範囲にわたって集計する）という英語の語感から。
