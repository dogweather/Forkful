---
title:                "日付を文字列に変換する"
date:                  2024-01-20T17:36:32.580204-07:00
model:                 gpt-4-1106-preview
simple_title:         "日付を文字列に変換する"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/elixir/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (何となぜ？)
日付を文字列に変換するのは、日付を読みやすい形式で保存、表示するプロセスです。プログラマーはログ、ユーザーインターフェイス、通信のためにこれを行います。

## How to (方法)
```Elixir
# Elixirの内蔵ライブラリを使った日付を文字列に変換
date = ~D[2023-04-05]
formatted_date = to_string(date)

IO.puts(formatted_date) # 出力: "2023-04-05"

# カスタムフォーマットを使用する
custom_format = "{YYYY}-{M}-{D}"
custom_formatted_date = Date.to_string(date, custom_format)

IO.puts(custom_formatted_date) # 出力: "2023-4-5"
```
デフォルトではISO8601形式ですが、カスタムフォーマットも利用できます。

## Deep Dive (深い潜在)
Elixirの日付と文字列変換は、Erlangのカレンダー機能に基づいています。現代のElixirバージョンでは、Dateモジュールを使用して簡単に日付を文字列へ（その逆も）変換できます。

以前のバージョンでは、外部ライブラリに依存する必要がありましたが、現在は標準ライブラリで完結しています。`Date.to_string/1`関数はISO8601フォーマットを使い、`Date.to_string/2`はカスタム形式を受け入れます。フォーマト指定子は `{YYYY}`, `{M}`, `{D}` のように使われ、それぞれ年、月、日を表します。

また、自然言語処理ライブラリやカスタムの日付関連ライブラリを使用することも可能です。これらはより高度なパターンや言語の特性に基づくフォーマットを提供しますが、ほとんどの基本的な用途にはElixirの標準機能で十分です。

## See Also (関連情報)
- Elixirの公式ドキュメント: [Date](https://hexdocs.pm/elixir/Date.html)
- Erlangのカレンダー機能: [Erlang -- calendar](http://erlang.org/doc/man/calendar.html)
- ISO8601についての詳細: [Wikipedia ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)