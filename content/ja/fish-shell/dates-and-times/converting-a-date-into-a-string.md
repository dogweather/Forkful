---
date: 2024-01-20 17:36:26.486971-07:00
description: "\u65E5\u4ED8\u304B\u3089\u6587\u5B57\u5217\u3078\u306E\u5909\u63DB\u306F\
  \u3001\u7279\u5B9A\u306E\u5F62\u5F0F\u306E\u65E5\u4ED8\u30C7\u30FC\u30BF\u3092\u308F\
  \u304B\u308A\u3084\u3059\u3044\u30C6\u30AD\u30B9\u30C8\u5F62\u5F0F\u306B\u3059\u308B\
  \u3053\u3068\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\u306E\
  \u5909\u63DB\u3092\u3001\u30ED\u30B0\u3001\u30EC\u30DD\u30FC\u30C8\u4F5C\u6210\u3001\
  \u307E\u305F\u306F\u30E6\u30FC\u30B6\u30FC\u30A4\u30F3\u30BF\u30FC\u30D5\u30A7\u30A4\
  \u30B9\u3067\u306E\u65E5\u4ED8\u8868\u793A\u306E\u305F\u3081\u306B\u884C\u3044\u307E\
  \u3059\u3002"
isCJKLanguage: true
lastmod: '2024-03-13T22:44:42.753169-06:00'
model: gpt-4-1106-preview
summary: "\u65E5\u4ED8\u304B\u3089\u6587\u5B57\u5217\u3078\u306E\u5909\u63DB\u306F\
  \u3001\u7279\u5B9A\u306E\u5F62\u5F0F\u306E\u65E5\u4ED8\u30C7\u30FC\u30BF\u3092\u308F\
  \u304B\u308A\u3084\u3059\u3044\u30C6\u30AD\u30B9\u30C8\u5F62\u5F0F\u306B\u3059\u308B\
  \u3053\u3068\u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u3053\u306E\
  \u5909\u63DB\u3092\u3001\u30ED\u30B0\u3001\u30EC\u30DD\u30FC\u30C8\u4F5C\u6210\u3001\
  \u307E\u305F\u306F\u30E6\u30FC\u30B6\u30FC\u30A4\u30F3\u30BF\u30FC\u30D5\u30A7\u30A4\
  \u30B9\u3067\u306E\u65E5\u4ED8\u8868\u793A\u306E\u305F\u3081\u306B\u884C\u3044\u307E\
  \u3059\u3002."
title: "\u65E5\u4ED8\u3092\u6587\u5B57\u5217\u306B\u5909\u63DB\u3059\u308B"
weight: 28
---

## How to: (方法：)
```Fish Shell
# 現在の日付と時刻を取得し、独自の形式で出力
set current_date (date)
echo $current_date

# 日付を YYYY-MM-DD 形式で出力
set formatted_date (date "+%Y-%m-%d")
echo $formatted_date
```

Sample Output:
```
Sun Mar 14 15:02:56 JST 2021
2021-03-14
```

## Deep Dive (深掘り)
過去、Unix/Linux 系のシェルでは日付と時刻の操作に `date` コマンドが使われてきました。Fish Shell でもこのコマンドを利用し、日付の文字列変換が可能です。他のプログラミング言語にも同様の機能がありますが、シェルスクリプトでは直接的な方法で扱えるのが魅力です。Fish では日付データを +オプションと組み合わせて、多様なフォーマットに対応することができます。

例えば：
- `%Y`: 年を4桁で表示。
- `%m`: 月を2桁で表示。
- `%d`: 日を2桁で表示。

これにより、ログファイルのタイムスタンプや、プログラムの出力を整形する際、柔軟性と読みやすさを提供します。

## See Also (関連項目)
- Fish Shell 公式ドキュメント: [https://fishshell.com/docs/current/index.html](https://fishshell.com/docs/current/index.html)
- `date` コマンドのマニュアルページ: [https://man7.org/linux/man-pages/man1/date.1.html](https://man7.org/linux/man-pages/man1/date.1.html)
- POSIX `strftime` フォーマット指定子: [https://pubs.opengroup.org/onlinepubs/9699919799/functions/strftime.html](https://pubs.opengroup.org/onlinepubs/9699919799/functions/strftime.html)
