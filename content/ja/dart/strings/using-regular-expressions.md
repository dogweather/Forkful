---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:57:05.276556-07:00
description: "Dart \u3067\u306E\u6B63\u898F\u8868\u73FE\uFF08regex\uFF09\u306F\u3001\
  \u6587\u5B57\u5217\u306E\u691C\u7D22\u304A\u3088\u3073\u64CD\u4F5C\u306B\u5F37\u529B\
  \u306A\u65B9\u6CD5\u3092\u63D0\u4F9B\u3057\u3001\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\
  \u304C\u8907\u96D1\u306A\u30C6\u30AD\u30B9\u30C8\u51E6\u7406\u30BF\u30B9\u30AF\u3092\
  \u52B9\u7387\u7684\u306B\u5B9F\u884C\u3067\u304D\u308B\u3088\u3046\u306B\u3057\u307E\
  \u3059\u3002regex\u2026"
lastmod: '2024-03-13T22:44:41.682929-06:00'
model: gpt-4-0125-preview
summary: "Dart \u3067\u306E\u6B63\u898F\u8868\u73FE\uFF08regex\uFF09\u306F\u3001\u6587\
  \u5B57\u5217\u306E\u691C\u7D22\u304A\u3088\u3073\u64CD\u4F5C\u306B\u5F37\u529B\u306A\
  \u65B9\u6CD5\u3092\u63D0\u4F9B\u3057\u3001\u30D7\u30ED\u30B0\u30E9\u30DE\u30FC\u304C\
  \u8907\u96D1\u306A\u30C6\u30AD\u30B9\u30C8\u51E6\u7406\u30BF\u30B9\u30AF\u3092\u52B9\
  \u7387\u7684\u306B\u5B9F\u884C\u3067\u304D\u308B\u3088\u3046\u306B\u3057\u307E\u3059\
  \u3002regex \u3092\u7406\u89E3\u3059\u308B\u3053\u3068\u3067\u3001\u958B\u767A\u8005\
  \u306F\u30C6\u30AD\u30B9\u30C8\u306E\u691C\u8A3C\u3001\u691C\u7D22\u30D1\u30BF\u30FC\
  \u30F3\u3001\u304A\u3088\u3073\u30C6\u30AD\u30B9\u30C8\u5909\u63DB\u3092\u8FC5\u901F\
  \u306B\u5B9F\u884C\u3067\u304D\u308B\u3088\u3046\u306B\u306A\u308A\u3001\u3053\u308C\
  \u306F\u30D5\u30A9\u30FC\u30E0\u306E\u51E6\u7406\u3001\u30C7\u30FC\u30BF\u306E\u89E3\
  \u6790\u3001\u304A\u3088\u3073\u73FE\u4EE3\u306E\u30A2\u30D7\u30EA\u30B1\u30FC\u30B7\
  \u30E7\u30F3\u3067\u306E\u4E00\u822C\u7684\u306A\u6587\u5B57\u5217\u64CD\u4F5C\u306B\
  \u4E0D\u53EF\u6B20\u3067\u3059\u3002."
title: "\u300C\u6B63\u898F\u8868\u73FE\u306E\u4F7F\u7528\u300D"
weight: 11
---

## 方法
Dart では、正規表現に `RegExp` クラスを使用します。文字列内のシンプルなパターンに一致する基本的な例を以下に示します：

```dart
void main() {
  var pattern = RegExp(r'\bDart\b');
  var text = 'Learning Dart programming is exciting.';

  if (pattern.hasMatch(text)) {
    print('Match found!');
  } else {
    print('No match found.');
  }
  // 出力：Match found!
}
```

文字列からマッチを抽出するには、`allMatches` メソッドを使用できます。このメソッドはマッチのイテラブルを返します：

```dart
void main() {
  var pattern = RegExp(r'\b\w+\b');
  var text = 'Dart is awesome!';

  var matches = pattern.allMatches(text);
  for (final match in matches) {
    print(match.group(0)); // これは一致した部分文字列を出力します。
  }
  // 出力：
  // Dart
  // is
  // awesome
}
```

テキストを置換するには、`replaceFirst` または `replaceAll` メソッドを使用します：

```dart
void main() {
  var pattern = RegExp(r'\bDart\b');
  var text = 'Dart is not just a dart.';
  
  // 最初の出現を置換
  var modifiedText = text.replaceFirst(pattern, 'Flutter');
  print(modifiedText); 
  // 出力: Flutter is not just a dart.

  // すべての出現を置換
  modifiedText = text.replaceAll(pattern, 'Flutter');
  print(modifiedText);
  // 出力: Flutter is not just a flutter.
}
```

正規表現パターンで文字列を分割するのは、`split` メソッドを使用すると簡単です：

```dart
void main() {
  var pattern = RegExp(r'\s+'); // 任意の空白文字に一致
  var text = 'Dart is fun';

  var parts = text.split(pattern);
  print(parts); 
  // 出力: [Dart, is, fun]
}
```

Dart の `RegExp` が直接サポートしていない複雑な解析や検証には、サードパーティのライブラリを検討するかもしれませんが、一般的な regex タスクには Dart の標準ライブラリがしばしば十分であり、正規表現を扱う際のその有用性と汎用性を強調しています。
