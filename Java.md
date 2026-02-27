# Java

## @NotBlank アノテーション

| 項目 | 値 |
|------|----|
| 理解度 | [x][x][x][ ] |
| 保存日 | 2026-02-24 |
| 最終復習 | 2026-02-27 |
| 次回復習 | 2026-03-06 |

**Q:** `@NotBlank` は何を検証するか？ `@NotNull` / `@NotEmpty` との違いは？

**A:** null でない、かつ空白文字を除いた文字列が1文字以上あることを検証する。3つの中で最も厳しい。
- `@NotNull` → null のみ NG
- `@NotEmpty` → null と `""` が NG
- `@NotBlank` → null、`""`、`"  "`（空白のみ）がすべて NG

**メモ:** Jakarta Validation のアノテーション。Spring Boot では `spring-boot-starter-validation` が必要。`@Valid` と組み合わせてリクエストボディの検証に使う。インターフェースのメソッドに付けることで「実装クラスはこの制約を満たせ」という契約を表現できる。
