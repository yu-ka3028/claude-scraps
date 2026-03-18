| 項目 | 値 |
|------|---|
| 理解度 | [x][x][ ][ ] |
| 保存日 | 2026-03-15 |
| 最終復習 | 2026-03-19 |
| 次回復習 | 2026-03-22 |

**Q:** useEffectのクリーンアップ関数とは何か、なぜ必要か？

**A:** `return () => {}` で返す関数。effectが再実行される前・コンポーネントがアンマウントされるときに実行される。接続したら切断、addEventListener したら removeEventListener をセットで書くことで、古い接続が残り続けるのを防ぐ。

**メモ:** `connect()→disconnect()`、`addEventListener→removeEventListener`、`setTimeout→clearTimeout` のようにペアで書く。[[React/フック-トップレベル制約.md]] で学んだuseEffectもフックのひとつ。
