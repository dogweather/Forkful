---
aliases:
- /zh/ruby/converting-a-string-to-lower-case/
date: 2024-01-20 17:39:06.180324-07:00
description: "\u5C06\u5B57\u7B26\u4E32\u8F6C\u6362\u4E3A\u5C0F\u5199\u662F\u6539\u53D8\
  \u5B57\u7B26\u4E32\u4E2D\u6240\u6709\u5927\u5199\u5B57\u7B26\u4E3A\u5C0F\u5199\u7684\
  \u8FC7\u7A0B\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u4E3B\u8981\u662F\u4E3A\u4E86\
  \u6807\u51C6\u5316\u8F93\u5165\u6570\u636E\uFF0C\u4FBF\u4E8E\u6BD4\u8F83\u548C\u641C\
  \u7D22\u3002"
isCJKLanguage: true
lastmod: 2024-02-18 23:08:59.587922
model: gpt-4-1106-preview
summary: "\u5C06\u5B57\u7B26\u4E32\u8F6C\u6362\u4E3A\u5C0F\u5199\u662F\u6539\u53D8\
  \u5B57\u7B26\u4E32\u4E2D\u6240\u6709\u5927\u5199\u5B57\u7B26\u4E3A\u5C0F\u5199\u7684\
  \u8FC7\u7A0B\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u4E3B\u8981\u662F\u4E3A\u4E86\
  \u6807\u51C6\u5316\u8F93\u5165\u6570\u636E\uFF0C\u4FBF\u4E8E\u6BD4\u8F83\u548C\u641C\
  \u7D22\u3002"
title: "\u5C06\u5B57\u7B26\u4E32\u8F6C\u6362\u4E3A\u5C0F\u5199"
---

{{< edit_this_page >}}

## What & Why? 什么和为什么？
将字符串转换为小写是改变字符串中所有大写字符为小写的过程。程序员这样做主要是为了标准化输入数据，便于比较和搜索。

## How to: 怎么做
```Ruby
# 将字符串转换为小写
example_str = "Hello World!"
lowercase_str = example_str.downcase

puts lowercase_str
# 输出: hello world!
```
简单的一行代码可以做到。

## Deep Dive 深入探讨
转换字符串为小写其实并不复杂。在Ruby早期版本，`.downcase` 就已经被引入。这个方法是由 `String` 类提供的，它能够处理多种字符编码，包括UTF-8，这对于支持多语言应用是重要的。

另外的方法，比如 `.downcase!` ，具有相同的功能但是会在原地修改字符串，如果字符串没变则返回nil。别忘记Ruby是一门灵活的语言，你还可以使用 `.swapcase` 来交换字符串中所有字母的大小写。

实际实现方面，`.downcase` 方法会考虑到语言特有的大小写转换规则。例如，在土耳其语中，大写的 'I' 转换成小写并不是 'i'，而是 'ı'。这意味着`.downcase`不仅仅是ASCII码的转换。在内部，Ruby代码会检查编码，并适当地调整字符，确保正确的转换。

## See Also 相关链接
- Ruby官方文档中关于String类的说明: [String Class - Ruby-Doc.org](https://ruby-doc.org/core-3.1.2/String.html)
