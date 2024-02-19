---
aliases:
- /ja/lua/using-a-debugger/
date: 2024-01-26 03:50:27.824306-07:00
description: "\u30C7\u30D0\u30C3\u30AC\u30FC\u306F\u30D7\u30ED\u30B0\u30E9\u30E0\u306E\
  \u5B9F\u884C\u3092\u691C\u67FB\u3057\u5236\u5FA1\u3059\u308B\u30C4\u30FC\u30EB\u3067\
  \u3001\u554F\u984C\u304C\u751F\u3058\u308B\u7B87\u6240\u3092\u5BB9\u6613\u306B\u7279\
  \u5B9A\u3067\u304D\u308B\u3088\u3046\u306B\u3057\u307E\u3059\u3002\u30D7\u30ED\u30B0\
  \u30E9\u30DE\u30FC\u306F\u30C7\u30D0\u30C3\u30AC\u30FC\u3092\u4F7F\u7528\u3057\u3066\
  \u30D0\u30B0\u3092\u6F70\u3057\u3001\u30B3\u30FC\u30C9\u30D5\u30ED\u30FC\u3092\u7406\
  \u89E3\u3057\u3001\u5F7C\u3089\u306E\u30B3\u30FC\u30C9\u304C\u30AF\u30EA\u30FC\u30F3\
  \u3067\u3042\u308B\u3053\u3068\u3092\u78BA\u8A8D\u3057\u307E\u3059\u3002"
lastmod: 2024-02-18 23:08:55.038019
model: gpt-4-0125-preview
summary: "\u30C7\u30D0\u30C3\u30AC\u30FC\u306F\u30D7\u30ED\u30B0\u30E9\u30E0\u306E\
  \u5B9F\u884C\u3092\u691C\u67FB\u3057\u5236\u5FA1\u3059\u308B\u30C4\u30FC\u30EB\u3067\
  \u3001\u554F\u984C\u304C\u751F\u3058\u308B\u7B87\u6240\u3092\u5BB9\u6613\u306B\u7279\
  \u5B9A\u3067\u304D\u308B\u3088\u3046\u306B\u3057\u307E\u3059\u3002\u30D7\u30ED\u30B0\
  \u30E9\u30DE\u30FC\u306F\u30C7\u30D0\u30C3\u30AC\u30FC\u3092\u4F7F\u7528\u3057\u3066\
  \u30D0\u30B0\u3092\u6F70\u3057\u3001\u30B3\u30FC\u30C9\u30D5\u30ED\u30FC\u3092\u7406\
  \u89E3\u3057\u3001\u5F7C\u3089\u306E\u30B3\u30FC\u30C9\u304C\u30AF\u30EA\u30FC\u30F3\
  \u3067\u3042\u308B\u3053\u3068\u3092\u78BA\u8A8D\u3057\u307E\u3059\u3002"
title: "\u30C7\u30D0\u30C3\u30AC\u30FC\u306E\u4F7F\u3044\u65B9"
---

{{< edit_this_page >}}

## 何となぜ？
デバッガーはプログラムの実行を検査し制御するツールで、問題が生じる箇所を容易に特定できるようにします。プログラマーはデバッガーを使用してバグを潰し、コードフローを理解し、彼らのコードがクリーンであることを確認します。

## 使い方：
Luaには組み込みのデバッガーがありませんが、ZeroBrane Studioのような外部のものを使用できます。これがそれを使う際の一例です：

```Lua
-- 故意にエラーを含むシンプルなLuaスクリプト
local function add(a, b)
    local result = a + b -- おっと、「b」を定義するのを忘れたふりをしましょう
    return result
end

print(add(10))
```

これをデバッガーで実行すると、問題が生じる箇所で実行が停止します。こんな感じのことが表示されます：

```
lua: example.lua:3: nil値に対する算術操作の試み (局所変数 'b')
スタックトレースバック:
	example.lua:3: 'add' 関数内
	example.lua:7: メインチャンク内
	[C]: in ?
```

ブレークポイントを設定し、コードを一歩ずつ進め、変数の値を覗き見ることで、頭を抱えることなくバグを追跡できます。

## より深く：
残念ながら、Luaのシンプルさはデバッグには及びません。しかし心配無用です、Luaコミュニティがサポートしてくれます。ZeroBrane Studio、LuaDecなどのツールはデバッグ機能を提供しています。歴史的に、デバッガーは最初のプログラムが問題を起こした直後に存在しており、開発者が手探りでコードを修正する手段を提供していました。

Luaでは、よく外部のデバッガーに頼ったり、開発環境にそれを組み込んだりします。たとえば、ZeroBrane StudioはLuaデバッガーを完全に統合したIDEです。それによりコードを一歩ずつ実行したり、ブレークポイントを設定したり、変数を監視することができます。実装の側では、デバッガーは通常、ブレークポイントやその他のデバッグ機能を挿入するためにフックを使用します。

代替手段は？ありますよ。昔ながらの`print`ステートメント、「printfデバッグ」とも呼ばれるものは、高尚なツールなしでも時には役立つことがあります。

## 参照
デバッグの旅を続けるには、以下をチェックしてみてください：

- ZeroBrane Studio: https://studio.zerobrane.com/
- Lua-users wikiのLuaコードデバッグについて: http://lua-users.org/wiki/DebuggingLuaCode
- Luaのマニュアルにある`debug`ライブラリのリファレンス：https://www.lua.org/manual/5.4/manual.html#6.10
