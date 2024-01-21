---
title:                "文字列の補間"
date:                  2024-01-20T17:51:29.476318-07:00
model:                 gpt-4-1106-preview
simple_title:         "文字列の補間"
programming_language: "PHP"
category:             "PHP"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ja/php/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (なにとなぜ？)

文字列展開とは、文字列の中に変数の内容や計算結果を挿入することです。プログラマは、動的なテキストメッセージを生成したり、出力をより読みやすくするためにこれを行います。

## How to: (やり方)

```PHP
<?php
$name = "Taro";
$age = 20;

// ダブルクォートを使用する
echo "こんにちは、${name}さん。あなたの年齢は${age}歳です。\n";

// シンプルな構文
echo "ハロー、$name。来年は " . ($age + 1) . " 歳になるね。\n";
?>

// 出力:
// こんにちは、Taroさん。あなたの年齢は20歳です。
// ハロー、Taro。来年は 21 歳になるね。
```

## Deep Dive (深掘り)

文字列展開は PHP 4 から利用可能で、簡単に変数値を文字列内に組み込める機能です。例えば、ハードコーディングされた文字列の代わりに、ユーザー名や設定など、変わる可能性があるデータを使用する場合に便利です。

代替手段として、コンカテネーション（点連結）を使えますが、コードが読みにくくなる可能性があります。また、`printf()` や `sprintf()` 関数を使用して、より複雑なフォーマットを生成することもできます。

文字列展開を行う際、ダブルクォートやヒアドキュメント内でのみ動作し、シングルクォートでは動作しません。変数が複雑な場合（例: 配列の要素やオブジェクトのプロパティ）は、波括弧 `{}` を使用して明示しなければならないことがあります。

## See Also (関連情報)

- PHP公式ドキュメントの文字列セクション: [PHP: Strings - Manual](https://www.php.net/manual/en/language.types.string.php)
- PHPの `printf` 関数について学ぶ: [PHP: printf - Manual](https://www.php.net/manual/en/function.printf.php)
- 変数のパースと文字列の展開: [PHP: Variable parsing - Manual](https://www.php.net/manual/en/language.types.string.php#language.types.string.parsing)