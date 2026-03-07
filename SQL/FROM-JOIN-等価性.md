# FROM-JOIN-等価性

| 項目 | 値 |
|------|---|
| 理解度 | [x][x][x][ ] |
| 保存日 | 2026-02-25 |
| 最終復習 | 2026-03-01 |
| 次回復習 | 2026-03-08 |

**Q:** `FROM A, B` と `FROM A, B WHERE A.id = B.id` はそれぞれ何と同義か？

**A:** `FROM A, B` は `CROSS JOIN`（直積）と同義。`WHERE` で絞り込むと結果は `INNER JOIN` と同じになるが、構文としては「CROSS JOIN → WHERE フィルタ」という処理。カンマ自体は INNER JOIN ではなく CROSS JOIN。

**メモ:** `FROM A, B WHERE ...` は「旧式の INNER JOIN 記法」と説明されることがあるが、それは結果が同じというだけ。構文的には CROSS JOIN + フィルタ。明示的な `INNER JOIN ... ON` の方が意図が伝わりやすく現代では推奨される。JOIN を適切に使わないアンチパターンは [[Jaywalking-アンチパターン]] を参照。
