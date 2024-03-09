---
title:                "使用关联数组"
date:                  2024-03-08T21:57:11.544790-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么?

在 Dart 中，关联数组通常被称为 Maps，是一种以键值对存储数据的数据结构。它们使程序员可以不通过索引而是通过键来访问元素，使得数据检索直观且高效，尤其是在处理每个元素都有唯一标识符的结构化数据时。

## 如何操作:

Dart 提供了一种直接的语法来创建和操作 Maps。下面是一些演示基本操作如创建、添加元素和获取值的例子。

```dart
void main() {
  // 创建一个 map
  var fruitColors = {
    'apple': 'red',
    'banana': 'yellow',
    'grape': 'purple'
  };

  // 添加一个新的键值对
  fruitColors['orange'] = 'orange';

  // 通过其键访问值
  print(fruitColors['apple']); // 输出：red

  // 更新值
  fruitColors['banana'] = 'green';

  // 遍历 Map
  fruitColors.forEach((fruit, color) {
    print('$fruit: $color');
  });
  // 示例输出：
  // apple: red
  // banana: green
  // grape: purple
  // orange: orange
}
```

对于复杂的数据结构或扩展的功能，Dart 程序员经常依赖于附加的库。其中一个库是 `collection`，它提供了高级集合类型和实用工具。尽管 `collection` 不改变处理 Maps 的基本方式，但它用实用函数和更复杂的集合类型丰富了它们。以下是您如何使用它来执行更具体的任务，如按其值对 Map 进行排序：

首先，确保 `collection` 包包含在您的 `pubspec.yaml` 文件中：

```yaml
dependencies:
  collection: ^1.15.0
```

然后，您可以按如下方式使用它：

```dart
import 'package:collection/collection.dart';

void main() {
  var fruitColors = {
    'apple': 'red',
    'banana': 'yellow',
    'grape': 'purple',
    'orange': 'orange'
  };

  // 按其值（颜色）对 Map 进行排序
  var sortedFruitsByColor = SplayTreeMap.from(
    fruitColors,
    (key1, key2) => fruitColors[key1]!.compareTo(fruitColors[key2]!)
  );

  print(sortedFruitsByColor);
  // 输出：
  // {orange: orange, apple: red, banana: yellow, grape: purple}
}
```

这个示例演示了基于它们的值对 Map 的条目进行排序，展示了 Dart 及其活跃的生态系统如何灵活地处理关联数组以进行更复杂的数据操作。
