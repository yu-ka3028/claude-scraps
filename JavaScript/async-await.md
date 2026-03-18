| 項目 | 値 |
|------|---|
| 理解度 | [x][ ][ ][ ] |
| 保存日 | 2026-03-15 |
| 最終復習 | 2026-03-19 |
| 次回復習 | 2026-03-20 |

**Q:** `async` / `await` とは何か、なぜ `.then()` より読みやすいのか？

**A:**
非同期処理を同期処理のように上から順に書ける構文。
- `async` — 関数が非同期処理を含むことを宣言。戻り値は必ず Promise になる
- `await` — Promise が解決するまでその行で待ってから次へ進む（関数の中だけを止め、アプリ全体はブロックしない）

`.then()` チェーンと違い、変数に値を直接受け取れるため、見た目が同期処理と同じになる。

**メモ:** `await` は `async` 関数の中でしか使えない。エラーは `try/catch` で捕捉する。Promise の糖衣構文なので、内部では Promise が動いている。

```js
async function main() {
  const data = await fetch(url)           // ここで待つ
  const result = await processData(data)  // 待つ
  await saveResult(result)                // 待つ
  console.log("完了")
}
```
