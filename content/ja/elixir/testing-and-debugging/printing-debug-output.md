---
aliases:
- /ja/elixir/printing-debug-output/
date: 2024-01-20 17:52:14.252444-07:00
description: "\u30D7\u30ED\u30B0\u30E9\u30E0\u3067\u4F55\u304C\u8D77\u3053\u3063\u3066\
  \u3044\u308B\u304B\u3092\u7406\u89E3\u3059\u308B\u305F\u3081\u3001\u30C7\u30D0\u30C3\
  \u30B0\u51FA\u529B\u3092\u4F7F\u3044\u307E\u3059\u3002\u3053\u308C\u306F\u3001\u554F\
  \u984C\u306E\u89E3\u6C7A\u3084\u30B3\u30FC\u30C9\u306E\u7406\u89E3\u3092\u52A9\u3051\
  \u308B\u305F\u3081\u306B\u884C\u308F\u308C\u307E\u3059\u3002"
isCJKLanguage: true
lastmod: 2024-02-18 23:08:54.645566
model: gpt-4-1106-preview
summary: "\u30D7\u30ED\u30B0\u30E9\u30E0\u3067\u4F55\u304C\u8D77\u3053\u3063\u3066\
  \u3044\u308B\u304B\u3092\u7406\u89E3\u3059\u308B\u305F\u3081\u3001\u30C7\u30D0\u30C3\
  \u30B0\u51FA\u529B\u3092\u4F7F\u3044\u307E\u3059\u3002\u3053\u308C\u306F\u3001\u554F\
  \u984C\u306E\u89E3\u6C7A\u3084\u30B3\u30FC\u30C9\u306E\u7406\u89E3\u3092\u52A9\u3051\
  \u308B\u305F\u3081\u306B\u884C\u308F\u308C\u307E\u3059\u3002"
title: "\u30C7\u30D0\u30C3\u30B0\u51FA\u529B\u3092\u8868\u793A\u3059\u308B"
---

{{< edit_this_page >}}

## What & Why? (何となぜ？)

プログラムで何が起こっているかを理解するため、デバッグ出力を使います。これは、問題の解決やコードの理解を助けるために行われます。

## How to: (やり方)

Elixirでは、`IO.inspect/2`と`IO.puts/1`をよく使います。これらはターミナルに情報を出力します。

```elixir
# 値を出力して変数をそのまま返します。
value = "Hello, World!"
IO.inspect(value)
# Output: "Hello, World!"

# 文字列を出力しますが、返り値は :ok となります。
IO.puts("Debugging my program")
# Output: Debugging my program
```

## Deep Dive (深堀り)

Elixirの前身であるErlangは、1987年に開発されました。開発の初期から、ElixirやErlangでは関数の戻り値としてデバッグ情報を出力することが一般的でした。`Logger`モジュールなどの代替手段もあります。これにより、設定に基づいてログレベルを柔軟に制御できます。

```elixir
# Loggerを使用して情報を出力する
require Logger

Logger.debug("Debug info: #{inspect(value)}")
```

他の言語とは異なり、Elixirの`IO.inspect/2`はデバッグ出力を行いつつ、値を変更せずに返す点が特徴です。つまり、デバッグ行を削除せずにコード内に残しても、プログラムの挙動に影響を与えません。

## See Also (参考)

- ElixirのIOモジュールのドキュメント: [https://hexdocs.pm/elixir/IO.html](https://hexdocs.pm/elixir/IO.html)
- ElixirのLoggerモジュールのドキュメント: [https://hexdocs.pm/logger/Logger.html](https://hexdocs.pm/logger/Logger.html)
