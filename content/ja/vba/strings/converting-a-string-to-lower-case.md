---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:51:29.259846-07:00
description: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\
  \u3068\u3044\u3046\u3053\u3068\u306F\u3001\u6587\u5B57\u5217\u5185\u306E\u3059\u3079\
  \u3066\u306E\u5927\u6587\u5B57\u3092\u305D\u308C\u3089\u306E\u5C0F\u6587\u5B57\u306B\
  \u5909\u63DB\u3059\u308B\u30D7\u30ED\u30BB\u30B9\u3092\u6307\u3057\u307E\u3059\u3002\
  \u3053\u306E\u30D7\u30ED\u30BB\u30B9\u306F\u3001\u30C7\u30FC\u30BF\u306E\u6B63\u898F\
  \u5316\u3001\u5927\u6587\u5B57\u3068\u5C0F\u6587\u5B57\u3092\u533A\u5225\u3057\u306A\
  \u3044\u6BD4\u8F03\u3001\u30E6\u30FC\u30B6\u30FC\u5165\u529B\u306E\u4E00\u8CAB\u6027\
  \u3092\u5411\u4E0A\u3055\u305B\u308B\u306A\u3069\u3001\u69D8\u3005\u306A\u30D7\u30ED\
  \u30B0\u30E9\u30DF\u30F3\u30B0\u30BF\u30B9\u30AF\u306B\u3068\u3063\u3066\u4E0D\u53EF\
  \u6B20\u3067\u3059\u3002"
lastmod: '2024-03-13T22:44:41.864952-06:00'
model: gpt-4-0125-preview
summary: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\
  \u3068\u3044\u3046\u3053\u3068\u306F\u3001\u6587\u5B57\u5217\u5185\u306E\u3059\u3079\
  \u3066\u306E\u5927\u6587\u5B57\u3092\u305D\u308C\u3089\u306E\u5C0F\u6587\u5B57\u306B\
  \u5909\u63DB\u3059\u308B\u30D7\u30ED\u30BB\u30B9\u3092\u6307\u3057\u307E\u3059\u3002\
  \u3053\u306E\u30D7\u30ED\u30BB\u30B9\u306F\u3001\u30C7\u30FC\u30BF\u306E\u6B63\u898F\
  \u5316\u3001\u5927\u6587\u5B57\u3068\u5C0F\u6587\u5B57\u3092\u533A\u5225\u3057\u306A\
  \u3044\u6BD4\u8F03\u3001\u30E6\u30FC\u30B6\u30FC\u5165\u529B\u306E\u4E00\u8CAB\u6027\
  \u3092\u5411\u4E0A\u3055\u305B\u308B\u306A\u3069\u3001\u69D8\u3005\u306A\u30D7\u30ED\
  \u30B0\u30E9\u30DF\u30F3\u30B0\u30BF\u30B9\u30AF\u306B\u3068\u3063\u3066\u4E0D\u53EF\
  \u6B20\u3067\u3059\u3002."
title: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B"
weight: 4
---

## 方法：
Visual Basic for Applications (VBA)では、`LCase`関数を使用して文字列を小文字に変換するのは簡単です。この関数は文字列を入力として受け取り、すべての大文字を小文字に変換した新しい文字列を返します。この基本的な例を見てみましょう：

```basic
Dim originalString As String
Dim lowerCaseString As String

originalString = "Hello, World!"
lowerCaseString = LCase(originalString)

Debug.Print lowerCaseString ' 出力: hello, world!
```

比較や代入で`LCase`を直接使用することも、コードを簡潔にするために可能です：

```basic
If LCase(userInput) = "yes" Then
    Debug.Print "User said yes"
End If
```

この二つ目の例は、入力を比較する前に小文字に変換することによって、ユーザー入力を大文字と小文字を区別しない方法で扱う方法を示しています。

## 詳細
`LCase`関数はVBAでの文字列操作の基盤となっており、言語の誕生以来のコア機能でした。`LCase`は、データ解析やユーザー入力処理のシナリオで一般的なケース変換タスクを簡素化します。`LCase`は様々なアプリケーションで小文字への文字変換のニーズに効果的に対応しながら、その制限と代替案を認識することも重要です。

例えば、`LCase`は英字アルファベットにはスムーズに機能しますが、より複雑な大文字と小文字のルールを持つ言語を扱う場合は、ケース変換のために適切なロケール設定で`StrConv`関数を使用することが追加で考慮される必要があります。

さらに、`str.lower()`を使用するPythonや、`string.toLowerCase()`を使用するJavaScriptのような言語から移行する際、プログラマーは`LCase`を直感的に見つけるかもしれませんが、メソッドのチェーンがないなど、VBAの特有の仕様を心に留めておく必要があります。

まとめると、他の言語では新しくてより強力な代替手段が存在するかもしれませんが、`LCase`はVBAで文字列を小文字に変換するための信頼できるシンプルな関数として残り、その全体の構文と機能のスキーマにうまく収まっています。
