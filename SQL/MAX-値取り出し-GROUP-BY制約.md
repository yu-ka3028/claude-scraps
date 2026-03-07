| 項目 | 値 |
|------|---|
| 理解度 | [x][x][x][ ] |
| 保存日 | 2026-02-25 |
| 最終復習 | 2026-03-07 |
| 次回復習 | 2026-03-14 |

**Q:** GROUP BY のある外側クエリでウィンドウ関数の結果を参照したいとき、なぜ `MAX` を使うのか？`COUNT` ではダメなのか？

**A:**
- GROUP BY は複数行を1行に潰す。潰された列は「どの値を使うか決められない」ため集約関数で1つの値に決める必要がある
- `COUNT(*) OVER()` の結果（`total_count`）は全行同じ値なので、`MAX` で包んで取り出しても値は変わらない（MIN/ANY_VALUE でも同じ）
- `COUNT(total_count)` は「NULLでない行数」を数えてしまい、値を取り出す目的に合わない
- `ANY_VALUE` が最も意図明確だが、慣習的に `MAX` が使われることが多い

**メモ:** `COUNT(*) OVER()` が全行同じ値になる理由は [[COUNT-OVER-PARTITION-BY]] を参照。
```
id | category | price
 1 | A        | 100
 2 | A        | 200   ← A グループに price が2つある
 3 | B        | 300
```
```sql
SELECT category, price      -- ❌ price はどっち？
FROM orders GROUP BY category

SELECT category, MAX(price) -- ✅ 最大値に決める
SELECT category, SUM(price) -- ✅ 合計に決める
SELECT category, COUNT(*)   -- ✅ 件数に決める
```
