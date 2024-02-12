---
title:                "字符串拼接"
aliases:
- zh/c-sharp/concatenating-strings.md
date:                  2024-01-20T17:34:18.096591-07:00
model:                 gpt-4-1106-preview
simple_title:         "字符串拼接"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/c-sharp/concatenating-strings.md"
---

{{< edit_this_page >}}

## What & Why? (是什么？为什么？)
字符串连接是把多个字符串拼成一个的过程。程序员这么做是为了合并文字，构建消息，或者生成动态内容。

## How to (如何操作)
在C#中，连接字符串可以用加号(`+`)，`String.Concat`，或者`StringBuilder`。看例子：

```C#
// 使用加号连接字符串
string greeting = "你好, " + "世界!";
Console.WriteLine(greeting);

// 使用String.Concat
string name = String.Concat("我", "的", "名字", "是", "小", "明");
Console.WriteLine(name);

// 使用StringBuilder
StringBuilder sb = new StringBuilder();
sb.Append("学习");
sb.Append("编程");
sb.Append("真");
sb.Append("有趣！");
string sentence = sb.ToString();
Console.WriteLine(sentence);
```

输出：
```
你好, 世界!
我的名字是小明
学习编程真有趣！
```

## Deep Dive (深入探讨)
历史上，字符串连接在编程早期不受重视，但随着时间，人们认识到其对性能的影响。C#早期版本与现在相比，字符串的连接方法有很大差异。比如`+`连接在编译时会变成`String.Concat`方法，但频繁使用时会导致性能问题。因此，大量的字符串操作推荐使用`StringBuilder`，因为它内部使用字符数组，避免了不必要的字符串复制。

备选方案包括`string.Join`和插值字符串`$""`（从C# 6开始）。`string.Join`可以连接字符串数组，插值字符串则提供了一种方便的方式来混合变量和字符串文字。

```C#
// string.Join 示例
var words = new[] {"加油,", "你", "可以", "做到"};
string encouragement = string.Join(" ", words);
Console.WriteLine(encouragement);

// 插值字符串 示例
string item = "书包";
int quantity = 3;
string message = $"我有{quantity}个{item}";
Console.WriteLine(message);
```

输出：
```
加油, 你 可以 做到
我有3个书包
```

## See Also (另请参阅)
- [MSDN 文档: 字符串插值](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/interpolated)
- [MSDN 文档: StringBuilder 类](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder)
- [MSDN 文档: String.Join 方法](https://docs.microsoft.com/en-us/dotnet/api/system.string.join)
- C#编程指南: [字符串](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
