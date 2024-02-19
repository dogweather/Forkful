---
aliases:
- /ja/lua/using-associative-arrays/
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:12:07.803046-07:00
description: "Lua\u306B\u304A\u3051\u308B\u9023\u60F3\u914D\u5217\u306F\u30C7\u30FC\
  \u30BF\u306E\u79D8\u5BC6\u306E\u63E1\u624B\u307F\u305F\u3044\u306A\u3082\u306E\u3067\
  \u3059\u3002\u30A4\u30F3\u30C7\u30C3\u30AF\u30B9\u306B\u3088\u3063\u3066\u6574\u7136\
  \u3068\u4E26\u3093\u3060\u6570\u5B57\u306E\u4EE3\u308F\u308A\u306B\u3001\u30AD\u30FC\
  \u3092\u81EA\u7531\u306B\u8A2D\u5B9A\u3067\u304D\u308B\u305F\u3081\u3001\u30C7\u30FC\
  \u30BF\u306E\u691C\u7D22\u304C\u975E\u5E38\u306B\u7C21\u5358\u306B\u306A\u308A\u307E\
  \u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u304C\u306A\u305C\u3053\u308C\u3092\
  \u4F7F\u7528\u3059\u308B\u306E\u304B\uFF1F\u305D\u308C\u306F\u3001\u6642\u3005\u3001\
  \u30C7\u30FC\u30BF\u3092\u884C\u756A\u53F7\u3067\u306F\u306A\u304F\u540D\u524D\u3067\
  \u547C\u3073\u51FA\u3059\u5FC5\u8981\u304C\u3042\u308B\u304B\u3089\u3067\u3059\u3002"
lastmod: 2024-02-18 23:08:55.027285
model: gpt-4-0125-preview
summary: "Lua\u306B\u304A\u3051\u308B\u9023\u60F3\u914D\u5217\u306F\u30C7\u30FC\u30BF\
  \u306E\u79D8\u5BC6\u306E\u63E1\u624B\u307F\u305F\u3044\u306A\u3082\u306E\u3067\u3059\
  \u3002\u30A4\u30F3\u30C7\u30C3\u30AF\u30B9\u306B\u3088\u3063\u3066\u6574\u7136\u3068\
  \u4E26\u3093\u3060\u6570\u5B57\u306E\u4EE3\u308F\u308A\u306B\u3001\u30AD\u30FC\u3092\
  \u81EA\u7531\u306B\u8A2D\u5B9A\u3067\u304D\u308B\u305F\u3081\u3001\u30C7\u30FC\u30BF\
  \u306E\u691C\u7D22\u304C\u975E\u5E38\u306B\u7C21\u5358\u306B\u306A\u308A\u307E\u3059\
  \u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u304C\u306A\u305C\u3053\u308C\u3092\u4F7F\
  \u7528\u3059\u308B\u306E\u304B\uFF1F\u305D\u308C\u306F\u3001\u6642\u3005\u3001\u30C7\
  \u30FC\u30BF\u3092\u884C\u756A\u53F7\u3067\u306F\u306A\u304F\u540D\u524D\u3067\u547C\
  \u3073\u51FA\u3059\u5FC5\u8981\u304C\u3042\u308B\u304B\u3089\u3067\u3059\u3002"
title: "\u9023\u60F3\u914D\u5217\u306E\u4F7F\u7528"
---

{{< edit_this_page >}}

## 何となぜ？

Luaにおける連想配列はデータの秘密の握手みたいなものです。インデックスによって整然と並んだ数字の代わりに、キーを自由に設定できるため、データの検索が非常に簡単になります。プログラマーがなぜこれを使用するのか？それは、時々、データを行番号ではなく名前で呼び出す必要があるからです。

## どのようにして：

Luaで連想配列（あるいはLua用語でのテーブル）を作成するのは簡単です。通常の数値インデックスを捨てて、自分で選んだキーを使います。これを見てください：

```Lua
-- 連想配列の作成
userInfo = {
  name = "Jamie",
  occupation = "Adventurer",
  level = 42
}

-- 要素へのアクセス
print(userInfo["name"]) -- Jamieを出力
print(userInfo.occupation) -- Adventurerを出力

-- 新しいキーと値の組み合わせの追加
userInfo["hobby"] = "Coding"
userInfo.favLang = "Lua"

-- 連想配列を繰り返し処理する
for key, value in pairs(userInfo) do
  print(key .. ": " .. value)
end
```

出力:
```
Jamie
Adventurer
name: Jamie
occupation: Adventurer
level: 42
hobby: Coding
favLang: Lua
```

クールな部分？データをあなたにとって意味のあるキーを使って操作することで、コードをより読みやすく、保守しやすくなります。

## 深掘り

Luaが登場したとき、テーブルを万能データ構造として導入し、開発者がデータを管理する方法を革命的に変えました。一部の言語では連想配列と配列が別のエンティティであるのに対し、Luaのテーブルはそれらの両方の役割を果たし、データ構造の風景を単純化します。

Luaテーブルを特に強力にするのはその柔軟性です。しかし、この柔軟性は特に大きなデータセットで効率性のためにより専門化されたデータ構造が望ましい場合、潜在的なパフォーマンスの問題を招く可能性があります。

Luaはリンクリストやハッシュマップなど、より従来のデータ構造を標準でサポートしていませんが、テーブル構造の適応性はこれらをテーブルを使って実装する必要がある場合に可能にします。ただし、記憶しておくべきは、大いなる力には大いなる責任が伴います。柔軟性を賢く使って、コードのパフォーマンスと可読性を保持してください。
