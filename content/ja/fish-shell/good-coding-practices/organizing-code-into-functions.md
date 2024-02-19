---
aliases:
- /ja/fish-shell/organizing-code-into-functions/
changelog:
- 2024-01-28, dogweather, reviewed and added links
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:01:54.914439-07:00
description: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u307E\u3068\u3081\u308B\u3053\
  \u3068\u306F\u3001\u7279\u5B9A\u306E\u30BF\u30B9\u30AF\u3092\u5B9F\u884C\u3059\u308B\
  \u305F\u3081\u306E\u30B9\u30AF\u30EA\u30D7\u30C8\u306E\u30D3\u30C3\u30C8\u3092\u675F\
  \u306D\u308B\u3053\u3068\u306B\u3064\u3044\u3066\u3067\u3059\u3002\u3053\u308C\u3092\
  \u884C\u3046\u7406\u7531\u306F\u3001\u30B3\u30FC\u30C9\u3092\u8AAD\u307F\u3084\u3059\
  \u304F\u3001\u30C6\u30B9\u30C8\u3057\u3084\u3059\u304F\u3001\u518D\u5229\u7528\u3057\
  \u3084\u3059\u304F\u3059\u308B\u305F\u3081\u3067\u3059\u3002\u8AB0\u3082\u304C\u30B3\
  \u30FC\u30C9\u30B9\u30D1\u30B2\u30C3\u30C6\u30A3\u306E\u6CBC\u3092\u6B69\u304D\u305F\
  \u3044\u3068\u601D\u3063\u3066\u3044\u308B\u308F\u3051\u3067\u306F\u3042\u308A\u307E\
  \u305B\u3093\u3002"
lastmod: 2024-02-18 23:08:55.314662
model: gpt-4-0125-preview
summary: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u307E\u3068\u3081\u308B\u3053\
  \u3068\u306F\u3001\u7279\u5B9A\u306E\u30BF\u30B9\u30AF\u3092\u5B9F\u884C\u3059\u308B\
  \u305F\u3081\u306E\u30B9\u30AF\u30EA\u30D7\u30C8\u306E\u30D3\u30C3\u30C8\u3092\u675F\
  \u306D\u308B\u3053\u3068\u306B\u3064\u3044\u3066\u3067\u3059\u3002\u3053\u308C\u3092\
  \u884C\u3046\u7406\u7531\u306F\u3001\u30B3\u30FC\u30C9\u3092\u8AAD\u307F\u3084\u3059\
  \u304F\u3001\u30C6\u30B9\u30C8\u3057\u3084\u3059\u304F\u3001\u518D\u5229\u7528\u3057\
  \u3084\u3059\u304F\u3059\u308B\u305F\u3081\u3067\u3059\u3002\u8AB0\u3082\u304C\u30B3\
  \u30FC\u30C9\u30B9\u30D1\u30B2\u30C3\u30C6\u30A3\u306E\u6CBC\u3092\u6B69\u304D\u305F\
  \u3044\u3068\u601D\u3063\u3066\u3044\u308B\u308F\u3051\u3067\u306F\u3042\u308A\u307E\
  \u305B\u3093\u3002"
title: "\u30B3\u30FC\u30C9\u3092\u95A2\u6570\u306B\u6574\u7406\u3059\u308B"
---

{{< edit_this_page >}}

## 何となぜ？
コードを関数にまとめることは、特定のタスクを実行するためのスクリプトのビットを束ねることについてです。これを行う理由は、コードを読みやすく、テストしやすく、再利用しやすくするためです。誰もがコードスパゲッティの沼を歩きたいと思っているわけではありません。

## 方法：
Fishで関数を書くには、`function`キーワードを使い、名前を付け、`end`で終了します。こちらが簡単なものです：

```fish
function hello
    echo "Hello, World!"
end

hello
```

出力：
```
Hello, World!
```

では、ユーザーにあいさつするようにしましょう：

```fish
function greet
    set user (whoami)
    echo "Hey there, $user!"
end

greet
```

出力：
```
Hey there, your_username!
```

セッションを跨いで保存するには、`funcsave greet`を使用します。

## 深掘り
Fish Shellの関数はミニスクリプトのようなものです。あらゆるものを詰め込むことができます。歴史的に、シェルスクリプティングの関数の概念は、繰り返しのタイピングとデバッグの何千時間も節約してきました。Pythonのようなプログラミング言語とは異なり、Shellの関数は構造よりも便利さについてです。

一部のシェル、例えばBashは、`function`または単に中括弧を使用します。Fishは`function ... end`に固執しています。明確で読みやすいです。Fish関数の内部では、パラメーター、`set -l`でのローカル変数、さらには別の関数内で関数を定義することさえできます。

`return`値は必要ありません。Fishはそれを重視していないからです。関数の出力がその返り値です。そして、将来のセッションで利用可能な永続的な関数を望むならば、`funcsave`を覚えておいてください。

## 参照

- 関数に関するfishチュートリアル: [https://fishshell.com/docs/current/tutorial.html#tut_functions](https://fishshell.com/docs/current/tutorial.html#functions)

### 関数コマンド

- [function](https://fishshell.com/docs/current/cmds/function.html) — 関数を作成
- [functions](https://fishshell.com/docs/current/cmds/functions.html) — 関数を表示または消去
- [funcsave](https://fishshell.com/docs/current/cmds/funcsave.html) — 関数の定義をユーザーの自動読み込みディレクトリに保存
- [funced](https://fishshell.com/docs/current/cmds/funced.html) — 関数を対話的に編集
