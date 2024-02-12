---
title:                "获取字符串的长度"
aliases:
- /zh/c-sharp/finding-the-length-of-a-string/
date:                  2024-01-20T17:46:55.436936-07:00
model:                 gpt-4-1106-preview
simple_title:         "获取字符串的长度"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/c-sharp/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (是什么？为什么？)
在C#中找出字符串的长度，就是确定它含有多少个字符。程序员经常这么做来验证输入、处理文本数据或限制输出。

## How to: (如何操作)
```C#
string greeting = "你好, 世界!";
int length = greeting.Length;
Console.WriteLine(length); // 输出: 7
```
字符串`"你好, 世界!"`的长度是7。`Length`属性计算出了字符的数量。注意，汉字也被计为一个字符。

## Deep Dive (深入探索)
早期的编程语言可能没有内建的字符串长度功能，需要手动遍历字符计数。在C#里，`.Length`属性给了我们一个快速、准确的方法来获取字符串长度。但是在处理有些编码（比如UTF-16）时，要注意一个逻辑上的字符可能由多个代码单元组成。除了`.Length`，其他技术，例如LINQ的`.Count()`方法，也能计算长度，但通常`.Length`是更直接、更快的选择。实现细节上，`.Length`返回的是一个`int`类型的数值，表示字符串中`Char`对象的数量。

## See Also (另请参阅)
- [Microsoft Docs on String.Length Property](https://docs.microsoft.com/en-us/dotnet/api/system.string.length)
- [Understanding Text in .NET](https://docs.microsoft.com/en-us/dotnet/standard/base-types/character-encoding)
- [Strings (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
