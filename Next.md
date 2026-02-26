# Next.js

## useEffect とサーバー環境

| 項目 | 値 |
|------|----|
| 理解度 | ▪︎◻︎◻︎◻︎ |
| 保存日 | 2026-02-27 |
| 最終復習 | 2026-02-27 |
| 次回復習 | 2026-02-28 |

**Q:** Next.js で `window` や `addEventListener` をコンポーネントの関数本体に直接書けないのはなぜか？

**A:** Next.js は最初の HTML をサーバーで生成するため、コンポーネント関数がサーバーでも実行される。サーバーには `window` が存在しないためエラーになる。`useEffect` の中はブラウザに届いた後にのみ実行されるので安全に使える。

```typescript
function AuthRedirect() {
  window.addEventListener(...) // ❌ 関数本体 = サーバーでも実行される

  useEffect(() => {
    window.addEventListener(...) // ✅ ブラウザに届いてから実行される
  }, []);
}
```

**メモ:**
- `useEffect` = 処理の実行タイミングを指定する場所（`useState` は値の保存）
- `addEventListener` は「イベントが起きたらこの関数を呼んで」という**登録**であって実行ではない
- `[]` = マウント時に1回だけ登録する
