---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:19.097332-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:42.750423-06:00'
model: gpt-4-0125-preview
summary: "\u6587\u5B57\u5217\u304B\u3089\u65E5\u4ED8\u3092\u89E3\u6790\u3059\u308B\
  \u3068\u306F\u3001\u6587\u5B57\u5217\u5185\u306B\u30A8\u30F3\u30B3\u30FC\u30C9\u3055\
  \u308C\u305F\u65E5\u4ED8\u60C5\u5831\u3092\u62BD\u51FA\u3057\u3001\u30D7\u30ED\u30B0\
  \u30E9\u30DF\u30F3\u30B0\u74B0\u5883\u304C\u8A8D\u8B58\u3057\u3066\u64CD\u4F5C\u3067\
  \u304D\u308B\u69CB\u9020\u5316\u3055\u308C\u305F\u5F62\u5F0F\u306B\u5909\u63DB\u3059\
  \u308B\u3053\u3068\u3092\u6307\u3057\u307E\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\
  \u30FC\u306F\u3001\u65E5\u4ED8\u306E\u6BD4\u8F03\u3001\u7B97\u8853\u3001\u30D5\u30A9\
  \u30FC\u30DE\u30C3\u30C8\u3001\u30ED\u30FC\u30AB\u30EA\u30BC\u30FC\u30B7\u30E7\u30F3\
  \u306A\u3069\u306E\u64CD\u4F5C\u3092\u53EF\u80FD\u306B\u3059\u308B\u305F\u3081\u306B\
  \u3053\u308C\u3092\u884C\u3044\u307E\u3059\u3002\u3053\u308C\u3089\u306F\u3001\u30B9\
  \u30B1\u30B8\u30E5\u30FC\u30EA\u30F3\u30B0\u3001\u30BF\u30A4\u30E0\u30B9\u30BF\u30F3\
  \u30D7\u3001\u5C65\u6B74\u30C7\u30FC\u30BF\u3092\u30BD\u30D5\u30C8\u30A6\u30A7\u30A2\
  \u3067\u52B9\u7387\u7684\u306B\u6271\u3046\u4E0A\u3067\u4E0D\u53EF\u6B20\u3067\u3059\
  \u3002."
title: "\u6587\u5B57\u5217\u304B\u3089\u65E5\u4ED8\u3092\u30D1\u30FC\u30B9\u3059\u308B"
weight: 30
---

## 方法：
Fish Shellでは、文字列から日付を解析するために特別に設計された組み込みコマンドはありません。代わりに、`date`（LinuxおよびmacOSで利用可能）のような外部ユーティリティに依存するか、より複雑な解析に向いている`GNU date`のような人気のサードパーティツールを活用します。以下がそのアプローチです：

**Fishで`date`を使用する：**

"YYYY-MM-DD"の形式の日付文字列を解析するには、`date`コマンドを`-d`（またはGNU dateでは`--date`）オプションに続けて文字列を指定して使用します。出力形式をフォーマットするには`+`オプションを使用します。

```fish
set date_str "2023-04-01"
date -d $date_str +"%A, %d %B %Y"
# 出力: Saturday, 01 April 2023
```

macOS用（`-j`と`-f`フラグに異なる形式が必要です）：

```fish
set date_str "2023-04-01"
date -j -f "%Y-%m-%d" $date_str +"%A, %d %B %Y"
# 出力: Saturday, 01 April 2023
```

**複雑な解析のためのGNU `date`の使用：**

GNU `date`は文字列形式に対してより柔軟です。入力形式を明示的に指定せずに、多くの一般的な日付文字列形式を自動的に検出することができます：

```fish
set complex_date_str "April 1, 2023 14:00"
date -d "$complex_date_str" '+%Y-%m-%d %H:%M:%S'
# 出力: 2023-04-01 14:00:00
```

ただし、自動的に認識されないかもしれない日付文字列を扱う場合や、入力形式について厳密な制御が必要な場合には、GNU `date`で入力形式を指定することは直接サポートされていません。そのような場合は、文字列を事前処理するか、より複雑な日付解析ルーティンのために設計された別のツールを使用することを検討してください。
