---
aliases:
- /zh/haskell/concatenating-strings/
date: 2024-01-20 17:35:19.261448-07:00
description: "\u5B57\u7B26\u4E32\u62FC\u63A5\u5C31\u662F\u5C06\u4E24\u4E2A\u6216\u591A\
  \u4E2A\u5B57\u7B26\u4E32\u7EC4\u5408\u6210\u4E00\u4E2A\u3002\u7A0B\u5E8F\u5458\u901A\
  \u5E38\u4F1A\u62FC\u63A5\u5B57\u7B26\u4E32\u4EE5\u663E\u793A\u590D\u6742\u7684\u6D88\
  \u606F\uFF0C\u7EC4\u6210\u4EE3\u7801\uFF0C\u6216\u8005\u6784\u9020\u6570\u636E\u3002"
isCJKLanguage: true
lastmod: 2024-02-18 23:08:59.162935
model: gpt-4-1106-preview
summary: "\u5B57\u7B26\u4E32\u62FC\u63A5\u5C31\u662F\u5C06\u4E24\u4E2A\u6216\u591A\
  \u4E2A\u5B57\u7B26\u4E32\u7EC4\u5408\u6210\u4E00\u4E2A\u3002\u7A0B\u5E8F\u5458\u901A\
  \u5E38\u4F1A\u62FC\u63A5\u5B57\u7B26\u4E32\u4EE5\u663E\u793A\u590D\u6742\u7684\u6D88\
  \u606F\uFF0C\u7EC4\u6210\u4EE3\u7801\uFF0C\u6216\u8005\u6784\u9020\u6570\u636E\u3002"
title: "\u5B57\u7B26\u4E32\u62FC\u63A5"
---

{{< edit_this_page >}}

## What & Why? 什么以及为什么?

字符串拼接就是将两个或多个字符串组合成一个。程序员通常会拼接字符串以显示复杂的消息，组成代码，或者构造数据。

## How to: 如何实现

在Haskell中，你可以使用 `++` 运算符或 `concat` 函数来拼接字符串。这里有一些例子：

```Haskell
main :: IO ()
main = do
  let hello = "你好"
  let world = "世界"
  putStrLn (hello ++ ", " ++ world ++ "!")
  putStrLn (concat [hello, ", ", world, "!"])
```

输出将会是：

```
你好, 世界!
你好, 世界!
```

## Deep Dive 深入探究

### 历史背景
Haskell的字符串拼接方法源自早期的函数式编程语言。`++`运算符可以追溯到Haskell的前身Miranda，这影响了Haskell的设计。

### 替代方案
虽然`++`用得很广泛，但在处理大量数据或效率至关重要的情况下，`Data.Text`和`Data.ByteString`提供了更高效的拼接方法。同时，Haskell的字符串插值库提供了其它途径来拼接字符串和数据。

### 实现细节
在`Prelude`库中，字符串被实现为字符的列表。所以，使用`++`来拼接字符串实际上是连接两个列表。如果你拼接的字符串很长，这可能会造成性能问题。

## See Also 相关链接

- Haskell中的 `Data.Text` 模块文档: [Data.Text](https://hackage.haskell.org/package/text) 
- 字符串插值库 `interpolate`: [interpolate](https://hackage.haskell.org/package/interpolate)
- 关于Haskell的性能问题讨论: [Haskell Wiki on Performance](https://wiki.haskell.org/Performance)
