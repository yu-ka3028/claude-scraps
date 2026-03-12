| 項目 | 値 |
|------|---|
| 理解度 | [x][ ][ ][ ] |
| 保存日 | 2026-03-12 |
| 最終復習 | 2026-03-12 |
| 次回復習 | 2026-03-13 |

**Q:** SPA と MPA の違いは何か？CSR/SSR とはどう対応する？

**A:**
- **MPA**（Multi-Page Application）: ページ遷移のたびにサーバーへリクエストし、完成済みHTMLを受け取って全体再描画する。Rails ERBが典型例。
- **SPA**（Single Page Application）: 最初に空のHTMLとJSを受け取り、以降はJSがルーティングして部分的にDOMを書き換える。ページ全体のリロードが起きない。

SPA は「アーキテクチャ」、CSR は「レンダリング手法」。SPA は通常 CSR で実装される。

**メモ:** [[SSR-vs-CSR]] も参照。Rails ERBの感覚は「ページ遷移のたびにHTMLが返ってくる」MPA。Vue（Vite）・React（Vite）はデフォルトで SPA + CSR。
