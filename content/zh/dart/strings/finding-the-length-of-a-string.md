---
title:                "查找字符串的长度"
date:                  2024-03-08T21:54:32.031276-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么?
在 Dart 中查找字符串的长度涉及确定给定字符串中代码单元（本质上，如果简单地考虑，则为字符数）的数量。程序员这样做是为了更精确地操作字符串，例如验证输入、截断显示文本或处理长度很重要的数据格式（例如，带长度前缀的消息的协议）。

## 如何操作:
Dart 通过使用 `length` 属性使得获取字符串长度变得简单直接。这里有一个基本示例：

```dart
void main() {
  String myString = "Hello, Dart!";
  print("The length of '\(myString)' is: \(myString.length)");
  // 输出: The length of 'Hello, Dart!' is: 12
}
```
此属性计算字符串中 UTF-16 代码单元的数量，这对于大多数常见用例而言，对应于字符串的长度。

对于更细微的文本处理，尤其是涉及超出基础多语言平面（BMP）的 Unicode 字符，请考虑使用 `characters` 包来计算字形簇，这可以更准确地代表用户感知到的字符。

首先，在你的 `pubspec.yaml` 中添加 `characters`：

```yaml
dependencies:
  characters: ^1.2.0
```

然后，像这样使用它：

```dart
import 'package:characters/characters.dart';

void main() {
  String myEmojiString = "👨‍👩‍👧‍👦 family";
  print("The length of '\(myEmojiString)' is: \(myEmojiString.characters.length)");
  // 输出: The length of '👨‍👩‍👧‍👦 family' is: 8
}
```

在此示例中，`myEmojiString.characters.length` 给出的长度是根据 Unicode 字形簇来计算的，这对于包含复杂字符的字符串（如表情符号或组合字符标记）来说，是更准确的表示方式。
