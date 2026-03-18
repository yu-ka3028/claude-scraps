| 項目 | 値 |
|------|---|
| 理解度 | [x][x][x][ ] |
| 保存日 | 2026-03-12 |
| 最終復習 | 2026-03-19 |
| 次回復習 | 2026-03-26 |

**Q:** Next.js の App Router とは何か？Rails のルーティングと何が違うか？

**A:**
Next.js のルーティング方式（v13〜）。`app/` フォルダ以下にファイルを置くとそのままURLルートになる「ファイルベースルーティング」。

Rails との比較:
- Rails: `config/routes.rb` に明示的にルートを書く
- App Router: ファイルを置くだけで自動的にルートになる（規約で解決）

役割は同じ「URLとコードの対応付け」だが書き方が真逆。

App Router を使うことで RSC・`'use client'` などサーバー/クライアントの使い分けが可能になる。素の React（Vite等）では CSR のみ。

**メモ:** 旧方式は Pages Router（`pages/` フォルダ）。[[RSC]] も参照。Rails の CoC（Convention over Configuration）の設計思想と共通している。
