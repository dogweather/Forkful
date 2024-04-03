---
date: 2024-01-26 03:39:55.387232-07:00
description: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7\u610F\u5473\u7740\
  \u5265\u79BB\u5B57\u7B26\u4E32\u6570\u636E\u90E8\u5206\u7684\u4EFB\u4F55\u5F15\u53F7\
  \u6807\u8BB0\u2014\u2014\u5355\u5F15\u53F7\uFF08' '\uFF09\u6216\u53CC\u5F15\u53F7\
  \uFF08\" \"\uFF09\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\u4E3A\u4E86\u5BF9\
  \u8F93\u5165\u8FDB\u884C\u6D88\u6BD2\uFF0C\u51C6\u5907\u6587\u672C\u4EE5\u4FBF\u5904\
  \u7406\uFF0C\u6216\u8005\u53BB\u9664\u53EF\u80FD\u5E72\u6270\u6570\u636E\u5904\u7406\
  \u548C\u64CD\u4F5C\u7684\u4E0D\u5FC5\u8981\u5B57\u7B26\u3002"
lastmod: '2024-03-13T22:44:47.801935-06:00'
model: gpt-4-0125-preview
summary: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7\u610F\u5473\u7740\
  \u5265\u79BB\u5B57\u7B26\u4E32\u6570\u636E\u90E8\u5206\u7684\u4EFB\u4F55\u5F15\u53F7\
  \u6807\u8BB0\u2014\u2014\u5355\u5F15\u53F7\uFF08' '\uFF09\u6216\u53CC\u5F15\u53F7\
  \uFF08\" \"\uFF09\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\u4E3A\u4E86\u5BF9\
  \u8F93\u5165\u8FDB\u884C\u6D88\u6BD2\uFF0C\u51C6\u5907\u6587\u672C\u4EE5\u4FBF\u5904\
  \u7406\uFF0C\u6216\u8005\u53BB\u9664\u53EF\u80FD\u5E72\u6270\u6570\u636E\u5904\u7406\
  \u548C\u64CD\u4F5C\u7684\u4E0D\u5FC5\u8981\u5B57\u7B26\u3002."
title: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7"
weight: 9
---

## 如何操作：
在Haskell中，我们可以编写一个函数，用于删除给定字符串中的所有引号。这就像是告诉引号走开，并确保它们明白这个暗示。

```Haskell
import Data.List (intercalate)
import Data.Char (isPunctuation)

removeQuotes :: String -> String
removeQuotes = filter (\c -> c /= '"' && c /= '\'')

main :: IO ()
main = do
    let stringWithQuotes = "Haskell said, \"Let's learn some functions!\""
    putStrLn $ removeQuotes stringWithQuotes
```

示例输出：

```
Haskell said, Lets learn some functions!
```

## 深入探讨
曾几何时，在编程中的字符串像互联网上的猫视频一样普遍之前，处理文本是一件棘手的事情。但随着编程语言的发展，字符串成为了编码的一个关键部分。然而，引号仍然是一把双刃剑——对于定义字符串来说是必不可少的，但作为实际数据包含在内时则是一种麻烦。

有其他方法吗？你可以选择性地行动，而不是像赶苍蝇一样拍打所有的引号。你可能希望只移除最外层的引号（一种典型的修剪）或处理字符串内的转义引号。

在实现上，上述的`removeQuotes`函数使用一个lambda来检查每个字符（`c`），看它是否是一个讨厌的引号，并据此过滤它们。这是一种直接的方法，但对于更大的文本或更复杂的规则，你可能会希望查看像`Parsec`这样的解析库，它们在文本处理中可以给你更多的细腻和能力。

## 另见：
- 对于正则表达式爱好者：[Text.Regex.Posix](https://hackage.haskell.org/package/regex-posix)
- Haskell字符串的温和介绍：[Learn You a Haskell for Great Good! - Starting Out](http://learnyouahaskell.com/starting-out#strings)
