---
date: 2024-01-26 03:38:31.160423-07:00
description: "\u5728C#\u4E2D\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7\
  \u610F\u5473\u7740\u4F60\u8981\u53BB\u6389\u5305\u88F9\u4F60\u6587\u5B57\u7684\u90A3\
  \u4E9B\u8BA8\u538C\u7684\u53CC\u5F15\u53F7\uFF08`\"`\uFF09\u6216\u5355\u5F15\u53F7\
  \uFF08`'`\uFF09\u3002\u7A0B\u5E8F\u5458\u8FD9\u4E48\u505A\u662F\u4E3A\u4E86\u6E05\
  \u7406\u6570\u636E\u3001\u4E3A\u6570\u636E\u5E93\u8F93\u5165\u505A\u51C6\u5907\uFF0C\
  \u6216\u8005\u4F7F\u5B57\u7B26\u4E32\u5B89\u5168\u5730\u8FDB\u884C\u8FDB\u4E00\u6B65\
  \u5904\u7406\uFF0C\u8FD9\u6837\u5F53\u4E00\u4E2A\u5076\u7136\u7684\u5F15\u53F7\u51FA\
  \u73B0\u65F6\uFF0C\u4E8B\u60C5\u5C31\u4E0D\u4F1A\u53D8\u5F97\u6DF7\u4E71\u3002"
lastmod: '2024-03-13T22:44:47.754170-06:00'
model: gpt-4-0125-preview
summary: "\u5728C#\u4E2D\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7\u610F\
  \u5473\u7740\u4F60\u8981\u53BB\u6389\u5305\u88F9\u4F60\u6587\u5B57\u7684\u90A3\u4E9B\
  \u8BA8\u538C\u7684\u53CC\u5F15\u53F7\uFF08`\"`\uFF09\u6216\u5355\u5F15\u53F7\uFF08\
  `'`\uFF09\u3002\u7A0B\u5E8F\u5458\u8FD9\u4E48\u505A\u662F\u4E3A\u4E86\u6E05\u7406\
  \u6570\u636E\u3001\u4E3A\u6570\u636E\u5E93\u8F93\u5165\u505A\u51C6\u5907\uFF0C\u6216\
  \u8005\u4F7F\u5B57\u7B26\u4E32\u5B89\u5168\u5730\u8FDB\u884C\u8FDB\u4E00\u6B65\u5904\
  \u7406\uFF0C\u8FD9\u6837\u5F53\u4E00\u4E2A\u5076\u7136\u7684\u5F15\u53F7\u51FA\u73B0\
  \u65F6\uFF0C\u4E8B\u60C5\u5C31\u4E0D\u4F1A\u53D8\u5F97\u6DF7\u4E71\u3002."
title: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7"
weight: 9
---

## 如何操作：
```csharp
string withQuotes = "\"Hello, World!\"";
Console.WriteLine($"Original: {withQuotes}");

// 移除双引号
string withoutDoubleQuotes = withQuotes.Replace("\"", "");
Console.WriteLine($"Without Double Quotes: {withoutDoubleQuotes}");

// 假如你的字符串原本就包含单引号，移除单引号
string withSingleQuotes = "'Hello, World!'";
string withoutSingleQuotes = withSingleQuotes.Replace("'", "");
Console.WriteLine($"Without Single Quotes: {withoutSingleQuotes}");
```

输出：
```
Original: "Hello, World!"
Without Double Quotes: Hello, World!
Without Single Quotes: Hello, World!
```

## 深入探讨
移除引号的概念既不新颖也不特别复杂，但它至关重要，因为引号经常被用来界定字符串。当一个带有未转义引号的字符串被包含在代码块或数据文件中时，它可能会过早终止字符串，导致错误或安全问题，如注入攻击。

从历史上看，处理引号一直是数据处理中验证和清理过程的一部分。虽然`.Replace()`方法对于从一个简单的字符串中抽出引号很直接，但你可能需要更先进的技术，如正则表达式，来处理更复杂的场景，比如嵌套引号或有条件的移除。

`.Replace()`的替代方法包括在你需要细粒度控制或处理的是模式而不是固定字符时使用`Regex`类的方法。例如，当处理转义字符时`Regex.Unescape()`可能派上用场。

在实现上，记住C#中的字符串是不可变的，意味着每次使用`.Replace()`时都会创建一个新字符串。对于小型或一次性操作，这没什么大不了的，但对于大型或众多字符串的性能来说，这是需要记在心上的。

## 另请参阅：
- [String.Replace 方法文档](https://docs.microsoft.com/en-us/dotnet/api/system.string.replace?view=netframework-4.8)
- [.NET中的正则表达式](https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expressions)
- [安全字符串处理最佳实践](https://www.owasp.org/index.php/Data_Validation)
