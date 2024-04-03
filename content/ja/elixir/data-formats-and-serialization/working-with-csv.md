---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:19:44.213202-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:41.639690-06:00'
model: gpt-4-0125-preview
summary: "CSV\uFF08\u30AB\u30F3\u30DE\u533A\u5207\u308A\u5024\uFF09\u30D5\u30A1\u30A4\
  \u30EB\u306E\u6271\u3044\u306B\u306F\u3001\u3053\u308C\u3089\u306E\u30D5\u30A1\u30A4\
  \u30EB\u304B\u3089\u306E\u8AAD\u307F\u53D6\u308A\u3068\u30C7\u30FC\u30BF\u306E\u66F8\
  \u304D\u8FBC\u307F\u304C\u542B\u307E\u308C\u3001\u30C7\u30FC\u30BF\u306E\u30A4\u30F3\
  \u30DD\u30FC\u30C8/\u30A8\u30AF\u30B9\u30DD\u30FC\u30C8\u3084\u30B7\u30F3\u30D7\u30EB\
  \u306A\u30B9\u30C8\u30EC\u30FC\u30B8\u30BD\u30EA\u30E5\u30FC\u30B7\u30E7\u30F3\u304C\
  \u5FC5\u8981\u306A\u30BF\u30B9\u30AF\u306B\u306F\u4E00\u822C\u7684\u306A\u5FC5\u8981\
  \u6027\u304C\u3042\u308A\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\
  \u3001\u30B7\u30B9\u30C6\u30E0\u9593\u306E\u30C7\u30FC\u30BF\u4EA4\u63DB\u3001\u8FC5\
  \u901F\u306A\u30C7\u30FC\u30BF\u7DE8\u96C6\u3001\u307E\u305F\u306F\u8EFD\u91CF\u3067\
  \u7C21\u5358\u306B\u64CD\u4F5C\u53EF\u80FD\u306A\u30C7\u30FC\u30BF\u5F62\u5F0F\u304C\
  \u6709\u5229\u306A\u72B6\u6CC1\u3067\u3001\u3053\u306E\u6A5F\u80FD\u3092\u6D3B\u7528\
  \u3057\u307E\u3059\u3002."
title: "CSV\u3068\u306E\u4F5C\u696D"
weight: 37
---

## 方法：
Elixirは、強力なパターンマッチングとパイプラインのサポートを備えているため、サードパーティのライブラリなしでもCSVファイルを効率的に扱うことができます。しかし、より高度なニーズに対しては、`nimble_csv`ライブラリが速くて簡潔な選択肢です。

### 外部ライブラリなしでCSVファイルを読む
Elixirの組み込み関数を使用してCSVファイルを読み取り、解析することができます：

```elixir
defmodule CSVReader do
  def read_file(file_path) do
    File.stream!(file_path)
    |> Stream.map(&String.trim_trailing/1)
    |> Stream.map(&String.split(&1, ","))
    |> Enum.to_list()
  end
end

# サンプル使用法
CSVReader.read_file("data.csv")
# 出力: [["Header1", "Header2"], ["Row1Value1", "Row1Value2"], ["Row2Value1", "Row2Value2"]]
```

### CSVファイルに書き込む
同様に、CSVファイルにデータを書き込むには：

```elixir
defmodule CSVWriter do
  def write_to_file(file_path, data) do
    File.open(file_path, [:write], fn file ->
      Enum.each(data, fn row ->
        IO.write(file, Enum.join(row, ",") <> "\n")
      end)
    end)
  end
end

# サンプル使用法
data = [["Header1", "Header2"], ["Value1", "Value2"], ["Value3", "Value4"]]
CSVWriter.write_to_file("output.csv", data)
# CSV形式のデータを含むoutput.csvを作成
```

### `nimble_csv`の使用
より複雑なCSVの扱いには、`nimble_csv`はCSVデータを扱うための強力で柔軟な方法を提供します。まず、`nimble_csv`を`mix.exs`の依存関係に追加し、`mix deps.get`を実行します：

```elixir
defp deps do
  [
    {:nimble_csv, "~> 1.2"}
  ]
end
```

`nimble_csv`でCSVデータを解析：

```elixir
defmodule MyCSVParser do
  NimbleCSV.define(MyParser, separator: ",", escape: "\\")

  def parse(file_path) do
    file_path
    |> File.stream!()
    |> MyParser.parse_stream()
    |> Enum.to_list()
  end
end

# サンプル使用法
MyCSVParser.parse("data.csv")
# nimble_csvを使用した出力は、パーサーの設定によりますが、一般的にはリストのリストやタプルのように見えます。
```

`nimble_csv`を使用してCSVデータを書き込むには、データを適切な形式に手動で変換してからファイルに書き込む必要があります。これはプレインなElixirの例と似ていますが、正しくフォーマットされたCSV行を生成するために`nimble_csv`を活用しています。

タスクの複雑さに適したアプローチを選択することで、ElixirでCSVファイルを非常に柔軟かつ強力に扱うことができます。
