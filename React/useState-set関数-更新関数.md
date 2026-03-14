| 項目 | 値 |
|------|---|
| 理解度 | [x][ ][ ][ ] |
| 保存日 | 2026-03-14 |
| 最終復習 | 2026-03-14 |
| 次回復習 | 2026-03-15 |

**Q:** useStateのset関数で更新関数を使うのはどんなとき？

**A:** 前のstateに依存する更新（+1/-1など）は `setState(prev => newValue)` の更新関数を使う。前のstateに依存しない場合（リセット、入力値）は直接値を渡せばOK。

**メモ:** `nextState` とは「次のstateになる値」のこと。更新関数を使う場合はその返り値がnextState。直接値を渡す方法では連続更新時に古いstateを参照してしまうことがある。[[React/フック-トップレベル制約.md]] と合わせてuseStateの基本。

```jsx
const [score, setScore] = useState(0);

setScore(prev => prev + 1); // 前のstateに依存 → 更新関数
setScore(prev => prev - 1);
setScore(0);                 // 前のstateに依存しない → 直接値
setName(e.target.value);
```
