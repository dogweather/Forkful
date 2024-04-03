---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:18.174574-07:00
description: "\u2026"
lastmod: '2024-03-13T22:44:41.654978-06:00'
model: gpt-4-0125-preview
summary: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B\
  \u3053\u3068\u306F\u3001\u4E0E\u3048\u3089\u308C\u305F\u6587\u5B57\u5217\u306E\u5168\
  \u3066\u306E\u6587\u5B57\u3092\u305D\u308C\u305E\u308C\u306E\u5C0F\u6587\u5B57\u306E\
  \u7B49\u4FA1\u7269\u306B\u5909\u63DB\u3059\u308B\u57FA\u672C\u7684\u306A\u64CD\u4F5C\
  \u3067\u3059\u3002\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u306F\u901A\u5E38\u3001\u3053\
  \u306E\u64CD\u4F5C\u3092\u5B9F\u884C\u3057\u3066\u5927\u6587\u5B57\u3068\u5C0F\u6587\
  \u5B57\u3092\u533A\u5225\u3057\u306A\u3044\u6BD4\u8F03\u3092\u884C\u3046\u305F\u3081\
  \u3001\u307E\u305F\u306F\u3055\u3089\u306A\u308B\u51E6\u7406\u306E\u305F\u3081\u306B\
  \u30C6\u30AD\u30B9\u30C8\u5165\u529B\u3092\u6A19\u6E96\u5316\u3059\u308B\u305F\u3081\
  \u306B\u884C\u3044\u307E\u3059\u3002\u3053\u308C\u306B\u3088\u308A\u3001\u30A2\u30D7\
  \u30EA\u30B1\u30FC\u30B7\u30E7\u30F3\u304C\u3088\u308A\u30E6\u30FC\u30B6\u30FC\u30D5\
  \u30EC\u30F3\u30C9\u30EA\u30FC\u306B\u306A\u308A\u3001\u30C7\u30FC\u30BF\u304C\u3088\
  \u308A\u4E00\u8CAB\u6027\u3092\u6301\u3061\u307E\u3059\u3002."
title: "\u6587\u5B57\u5217\u3092\u5C0F\u6587\u5B57\u306B\u5909\u63DB\u3059\u308B"
weight: 4
---

## 方法：
Dartでは、`String` クラスによって提供される `toLowerCase()` メソッドを使用して、文字列を小文字に変換することができます。このメソッドは、全ての大文字を小文字に変換した新しい文字列を返します。これがどのように機能するか、簡単な例で見てみましょう：

```dart
void main() {
  String originalString = "Hello, World!";
  String lowerCaseString = originalString.toLowerCase();

  print(lowerCaseString);  // 出力: hello, world!
}
```

Dartでは、文字列を小文字に変換するなどの基本的な文字列操作タスクに外部ライブラリを要求しません。なぜなら、標準ライブラリの `String` クラスは非常に包括的だからです。しかし、ロケール固有のルールを含むより複雑な操作については、国際化およびローカライゼーション機能を提供する `intl` パッケージを検討することができます。これには、ロケールに基づいた大小文字変換も含まれます：

`intl` を使用するには、それをあなたの `pubspec.yaml` ファイルに追加します：

```yaml
dependencies:
  intl: ^0.17.0
```

次に、特定のロケールに基づいて文字列を小文字に変換するために `toLocaleLowerCase()` メソッドを使用することができます：

```dart
import 'package:intl/intl.dart';

void main() {
  String originalString = "İstanbul";
  
  // トルコ語のロケール
  print(Intl.withLocale('tr', () => originalString.toLowerCase())); // 出力: istanbul
  
  // デフォルトのロケール (en)
  print(originalString.toLowerCase()); // 出力: i̇stanbul
}
```

この例では、トルコ語のロケールがドットなしの 'i' を正しく扱うことを示しており、国際化されたアプリケーションでのロケールに意識した変換の重要性を浮き彫りにしています。
