# Claude Code Scraps

Claude Code のセッション中に出会った概念・用語を記録し、スペースドリピティション的に復習するための個人学習管理システム。CLAUDE.md と skills だけで動きます。

---

## 概要

AI を使い始めてから、自分のスキルを超えた成果物が出るようになった。
生まれたギャップを広い範囲の学習で一気に埋めようとするより、その場で気になったことをひとつ拾って、忘れる前に繰り返す方が効率がいいのではと思い、Claude Code セッションの中に記録と復習を埋め込んでみました。

**課題:**
- TIL は書いて終わりで読み返さない
- 専用アプリへの入力はコンテキストスイッチが発生して続かなくなる

**解決策:**
Claude Code セッション中に「これ気になった」と思った瞬間に保存 → スペースドリピティションで定着まで追跡。

---

## ファイル構成

```
.
├── CLAUDE.md                        # ルール定義（Claudeへの指示）
├── _index.md                        # 全スクラップの復習日・理解度を一元管理
├── _template.md                     # 新規スクラップファイルのテンプレート
├── _archive/                        # 理解度[x][x][x][x]になったスクラップの保管庫
├── _notebooklm/                     # /notebooklm-scrap の出力先
├── _radio/                          # /radio-scrap の出力先
├── _reports/                        # /report-scrap の出力先
├── SQL/                             # カテゴリ別フォルダ（1スクラップ = 1ファイル）
├── Web/
├── JavaScript/
└── .claude/
    └── skills/
        ├── status-scrap/            # /status-scrap コマンド
        ├── review-scrap/            # /review-scrap コマンド
        ├── report-scrap/            # /report-scrap コマンド
        ├── notebooklm-scrap/        # /notebooklm-scrap コマンド
        ├── radio-scrap/             # /radio-scrap コマンド
        └── link-scrap/              # /link-scrap コマンド
```

---

## 使い方

### 1. スクラップを保存する

セッション中に「スクラップに保存して」と言うだけで、Q/A 形式に整理して `git commit & push` まで実行する。

**理解度レベル:**

| レベル | 意味 | 次回復習 |
|--------|------|----------|
| `[x][ ][ ][ ]` | 保存したばかり | 1日後 |
| `[x][x][ ][ ]` | 概要は言える | 3日後 |
| `[x][x][x][ ]` | 自分の言葉で説明できる | 7日後 |
| `[x][x][x][x]` | 完全に定着 → `_archive/` へ移動 | 出題しない |

### 2. 今日の復習件数を確認する

```
/status-scrap
```

### 3. 復習セッションを開始する

```
/review-scrap
```

1問ずつ出題 → 回答 → フィードバック → 理解度申告 → ファイル更新のサイクル。
`[x][x][x][x]` を申告すると `_archive/` に自動移動され、以降は出題されない。

### 4. 学習レポートを生成する

```
/report-scrap [week|2weeks|month]
```

活動サマリー・理解度分布・次の学習提案を表示。

### 5. NotebookLM 用原稿を生成する

```
/notebooklm-scrap
```

全スクラップを意味的にグルーピングし、`_notebooklm/` に音声読み上げ原稿を生成する。

### 6. ラジオ原稿を生成する

```
/radio-scrap
```

全スクラップを横断したラジオ番組形式の原稿を `_radio/YYYY-MM-DD.md` に生成する。NotebookLM の Audio Overview に貼り付けて15分前後の音声を生成することを想定。

### 7. スクラップ間のリンクを整備する

```
/link-scrap
```

全スクラップを横断して読み込み、関連するファイル同士のメモ欄に `[[ファイル名]]` を追加する。Obsidian がそれをグラフに自動反映する。スクラップが増えてきたタイミングで定期的に実行する。

---

## スクラップのフォーマット

```markdown
| 項目 | 値 |
|------|---|
| 理解度 | [x][ ][ ][ ] |
| 保存日 | YYYY-MM-DD |
| 最終復習 | YYYY-MM-DD |
| 次回復習 | YYYY-MM-DD |

**Q:** {質問文}

**A:** {回答}

**メモ:** {補足・背景・使用例など（省略可）}
```

---

## このリポジトリを参考にする

以下のファイルを自分のリポジトリにコピーすると同じ仕組みが使えます。

```
CLAUDE.md
_template.md
_index.md
.claude/skills/status-scrap/SKILL.md
.claude/skills/review-scrap/SKILL.md
.claude/skills/report-scrap/SKILL.md
.claude/skills/notebooklm-scrap/SKILL.md
.claude/skills/radio-scrap/SKILL.md
.claude/skills/link-scrap/SKILL.md
```
