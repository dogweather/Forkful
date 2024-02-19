---
aliases:
- /ja/fish-shell/getting-the-current-date/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:34.615080-07:00
description: "\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u3067\u73FE\u5728\u306E\u65E5\
  \u4ED8\u3092\u53D6\u5F97\u3059\u308B\u3053\u3068\u306F\u3001\u30B7\u30B9\u30C6\u30E0\
  \u306E\u65E5\u4ED8\u3068\u6642\u523B\u306E\u30C7\u30FC\u30BF\u3092\u53D6\u5F97\u3057\
  \u3066\u64CD\u4F5C\u3059\u308B\u305F\u3081\u306E\u57FA\u672C\u7684\u306A\u4F5C\u696D\
  \u3067\u3059\u3002\u30B9\u30AF\u30EA\u30D7\u30C8\u3084\u81EA\u52D5\u5316\u30BF\u30B9\
  \u30AF\u3067\u306F\u3001\u30BF\u30A4\u30E0\u30B9\u30BF\u30F3\u30D7\u306E\u751F\u6210\
  \u3001\u30BF\u30B9\u30AF\u306E\u30B9\u30B1\u30B8\u30E5\u30FC\u30EA\u30F3\u30B0\u3001\
  \u30ED\u30B0\u306E\u4F5C\u6210\u306B\u4E0D\u53EF\u6B20\u3067\u3059\u3002"
lastmod: 2024-02-18 23:08:55.319267
model: gpt-4-0125-preview
summary: "\u30D7\u30ED\u30B0\u30E9\u30DF\u30F3\u30B0\u3067\u73FE\u5728\u306E\u65E5\
  \u4ED8\u3092\u53D6\u5F97\u3059\u308B\u3053\u3068\u306F\u3001\u30B7\u30B9\u30C6\u30E0\
  \u306E\u65E5\u4ED8\u3068\u6642\u523B\u306E\u30C7\u30FC\u30BF\u3092\u53D6\u5F97\u3057\
  \u3066\u64CD\u4F5C\u3059\u308B\u305F\u3081\u306E\u57FA\u672C\u7684\u306A\u4F5C\u696D\
  \u3067\u3059\u3002\u30B9\u30AF\u30EA\u30D7\u30C8\u3084\u81EA\u52D5\u5316\u30BF\u30B9\
  \u30AF\u3067\u306F\u3001\u30BF\u30A4\u30E0\u30B9\u30BF\u30F3\u30D7\u306E\u751F\u6210\
  \u3001\u30BF\u30B9\u30AF\u306E\u30B9\u30B1\u30B8\u30E5\u30FC\u30EA\u30F3\u30B0\u3001\
  \u30ED\u30B0\u306E\u4F5C\u6210\u306B\u4E0D\u53EF\u6B20\u3067\u3059\u3002"
title: "\u73FE\u5728\u306E\u65E5\u4ED8\u306E\u53D6\u5F97"
---

{{< edit_this_page >}}

## 何となぜ？
プログラミングで現在の日付を取得することは、システムの日付と時刻のデータを取得して操作するための基本的な作業です。スクリプトや自動化タスクでは、タイムスタンプの生成、タスクのスケジューリング、ログの作成に不可欠です。

## 方法：
Fish Shellは、必要に応じて出力の形式を整形する柔軟性を提供する`date`のような外部コマンドを利用して現在の日付を取得します。使い方は以下の通りです：

```fish
# デフォルト形式で現在の日付を表示
echo (date)

# 出力例：Wed 25 Oct 2023 15:42:03 BST
```

日付の形式をカスタマイズするには、フォーマット指定子に続けて`+`オプションを使用できます：

```fish
# YYYY-MM-DD形式で現在の日付を表示
echo (date "+%Y-%m-%d")

# 出力例：2023-10-25
```

タイムスタンプの取り扱いや日付演算のようなもっと複雑なタスクに対しては、スクリプティングの性質上、Fish Shellは`date`のような外部ツールに頼っています。現在のUNIXタイムスタンプを取得する例を以下に示します：

```fish
# 現在のUNIXタイムスタンプを取得
echo (date "+%s")

# 出力例：1666710123
```

そして`date`を使って現在の日付に一日を加えるには：

```fish
# 現在の日付に一日加える
echo (date -d "+1 day" "+%Y-%m-%d")

# 出力例：2023-10-26
```

注：例ではGNU coreutilsで動作する`date`コマンドのオプションを使用しています。macOSなど、デフォルトでBSD dateコマンドを使用する他の環境ではオプションが異なる場合があります。常に`date --help`またはmanページを参照して、ご自身の環境に特有の詳細を確認してください。
