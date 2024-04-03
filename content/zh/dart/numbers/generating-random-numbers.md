---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:37.181099-07:00
description: "\u5728 Dart \u4E2D\u751F\u6210\u968F\u673A\u6570\u610F\u5473\u7740\u521B\
  \u5EFA\u6570\u503C\u65F6\uFF0C\u5B83\u4EEC\u662F\u4E0D\u53EF\u9884\u6D4B\u7684\uFF0C\
  \u5E76\u4E14\u5728\u6BCF\u6B21\u6267\u884C\u65F6\u90FD\u4E0D\u540C\u3002\u7A0B\u5E8F\
  \u5458\u5229\u7528\u8FD9\u9879\u529F\u80FD\u6709\u591A\u79CD\u539F\u56E0\uFF0C\u4ECE\
  \u5728\u6D4B\u8BD5\u73AF\u5883\u4E2D\u6A21\u62DF\u771F\u5B9E\u4E16\u754C\u573A\u666F\
  \uFF0C\u5230\u542F\u7528\u6E38\u620F\u673A\u5236\uFF0C\u4EE5\u53CA\u901A\u8FC7\u968F\
  \u673A\u6027\u5728\u52A0\u5BC6\u64CD\u4F5C\u4E2D\u786E\u4FDD\u5B89\u5168\u6027\u3002"
lastmod: '2024-03-13T22:44:47.412797-06:00'
model: gpt-4-0125-preview
summary: "\u5728 Dart \u4E2D\u751F\u6210\u968F\u673A\u6570\u610F\u5473\u7740\u521B\
  \u5EFA\u6570\u503C\u65F6\uFF0C\u5B83\u4EEC\u662F\u4E0D\u53EF\u9884\u6D4B\u7684\uFF0C\
  \u5E76\u4E14\u5728\u6BCF\u6B21\u6267\u884C\u65F6\u90FD\u4E0D\u540C\u3002\u7A0B\u5E8F\
  \u5458\u5229\u7528\u8FD9\u9879\u529F\u80FD\u6709\u591A\u79CD\u539F\u56E0\uFF0C\u4ECE\
  \u5728\u6D4B\u8BD5\u73AF\u5883\u4E2D\u6A21\u62DF\u771F\u5B9E\u4E16\u754C\u573A\u666F\
  \uFF0C\u5230\u542F\u7528\u6E38\u620F\u673A\u5236\uFF0C\u4EE5\u53CA\u901A\u8FC7\u968F\
  \u673A\u6027\u5728\u52A0\u5BC6\u64CD\u4F5C\u4E2D\u786E\u4FDD\u5B89\u5168\u6027\u3002\
  ."
title: "\u751F\u6210\u968F\u673A\u6570"
weight: 12
---

## 如何操作：
Dart 的核心库支持使用 `dart:math` 中找到的 `Random` 类来生成随机数。这里有一个基本示例：

```dart
import 'dart:math';

void main() {
  var rand = Random();
  int randomNumber = rand.nextInt(100); // 生成一个 0 到 99 之间的随机整数
  double randomDouble = rand.nextDouble(); // 生成一个 0.0 到 1.0 之间的随机双精度浮点数
  print(randomNumber);
  print(randomDouble);
}
```

*示例输出：（每次运行都会变化）*

```
23
0.6722390975465775
```

对于需要加密随机性的用例，Dart 提供了 `Random.secure` 构造函数：

```dart
import 'dart:math';

void main() {
  var secureRand = Random.secure();
  int secureRandomNumber = secureRand.nextInt(100);
  print(secureRandomNumber);
}
```

*示例输出：（每次运行都会变化）*

```
45
```

如果你在处理 Flutter 项目或需要更复杂的随机性，你可能会发现 `faker` 包对于生成广泛的随机数据（如名字、地址和日期）很有用。

要使用 `faker`，首先，在你的 `pubspec.yaml` 文件中添加它：

```yaml
dependencies:
  faker: ^2.0.0
```

然后，按照如下方式导入并使用它：

```dart
import 'package:faker/faker.dart';

void main() {
  final faker = Faker();
  print(faker.person.name()); // 生成一个随机名字
  print(faker.address.city()); // 生成一个随机城市名
}
```

*示例输出：*

```
Josie Runolfsdottir
East Lysanne
```
