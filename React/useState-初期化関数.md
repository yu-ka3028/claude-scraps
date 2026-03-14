| 項目 | 値 |
|------|---|
| 理解度 | [x][ ][ ][ ] |
| 保存日 | 2026-03-14 |
| 最終復習 | 2026-03-14 |
| 次回復習 | 2026-03-15 |

**Q:** `useState(heavyCalc)` と `useState(heavyCalc())` の違いは？

**A:** `useState(heavyCalc)` は初期化関数として渡すため、初回レンダリングのみ実行される。`useState(heavyCalc())` は毎レンダリングで実行されるが、結果は初回しか使われない。

**メモ:** localStorageの読み込みや重い計算を初期値にしたいときは、`useState(fn)` の形で関数を渡す。[[useState-set関数-更新関数]] と合わせて `useState` の基本動作として押さえておく。
