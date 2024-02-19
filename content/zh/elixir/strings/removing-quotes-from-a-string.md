---
aliases:
- /zh/elixir/removing-quotes-from-a-string/
date: 2024-01-26 03:38:40.842944-07:00
description: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u5254\u9664\u5F15\u53F7\u610F\u5473\u7740\
  \u53BB\u9664\u90A3\u4E9B\u989D\u5916\u7684\u5305\u88C5\u5668\uFF0C\u4EE5\u83B7\u53D6\
  \u5185\u90E8\u7684\u5E72\u51C0\u6587\u672C\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\
  \u662F\u4E3A\u4E86\u6E05\u6D01\u8F93\u5165\u3001\u907F\u514D\u9519\u8BEF\u5E76\u4E3A\
  \u5904\u7406\u505A\u51C6\u5907\uFF0C\u5728\u8FD9\u4E9B\u5904\u7406\u4E2D\uFF0C\u5F15\
  \u53F7\u662F\u9EBB\u70E6\u800C\u975E\u7279\u6027\u3002"
lastmod: 2024-02-18 23:08:58.855435
model: gpt-4-0125-preview
summary: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u5254\u9664\u5F15\u53F7\u610F\u5473\u7740\
  \u53BB\u9664\u90A3\u4E9B\u989D\u5916\u7684\u5305\u88C5\u5668\uFF0C\u4EE5\u83B7\u53D6\
  \u5185\u90E8\u7684\u5E72\u51C0\u6587\u672C\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\
  \u662F\u4E3A\u4E86\u6E05\u6D01\u8F93\u5165\u3001\u907F\u514D\u9519\u8BEF\u5E76\u4E3A\
  \u5904\u7406\u505A\u51C6\u5907\uFF0C\u5728\u8FD9\u4E9B\u5904\u7406\u4E2D\uFF0C\u5F15\
  \u53F7\u662F\u9EBB\u70E6\u800C\u975E\u7279\u6027\u3002"
title: "\u4ECE\u5B57\u7B26\u4E32\u4E2D\u79FB\u9664\u5F15\u53F7"
---

{{< edit_this_page >}}

## 什么及为什么？
从字符串中剔除引号意味着去除那些额外的包装器，以获取内部的干净文本。程序员这样做是为了清洁输入、避免错误并为处理做准备，在这些处理中，引号是麻烦而非特性。

## 如何操作：
Elixir没有内建的“移除引号”函数，但利用模式匹配或`String`函数自行实现却很简单。看看这些代码片段：

```elixir
# 使用模式匹配
def unquote_string("\"" <> quoted_string <> "\""), do: quoted_string
def unquote_string("'" <> quoted_string <> "'"), do: quoted_string
def unquote_string(quoted_string), do: quoted_string

# 示例使用
unquote_string("\"你好，世界！\"") # => "你好，世界！"
unquote_string("'你好，世界！'")   # => "你好，世界！"

# 使用String.trim/1
def unquote_string(string), do: String.trim(string, "'\"")

# 示例使用
unquote_string("\"你好，世界！\"") # => "你好，世界！"
unquote_string("'你好，世界！'")   # => "你好，世界！"
```

两种方法的输出将是：
```
"你好，世界！"
```

## 深入了解
回到过去，字符串中的引号是一个雷区——处理不当，轰，语法错误或安全漏洞。在Elixir中，模式匹配像处理乐高积木一样处理你的字符串，让你可以准确地拆分和重建。它强大的`String`模块也很方便，灵活地使用`trim`函数去除引号。其他选择？正则表达式可以轻松处理引号，外部库如果你需要超出基本剥离的功能，可能会提供额外的火力。

## 另见
深入了解这些：
- [Elixir的String模块](https://hexdocs.pm/elixir/String.html)
- [了解更多关于Elixir中的模式匹配](https://elixir-lang.org/getting-started/pattern-matching.html)
- [Elixir中的正则表达式（Regex模块）](https://hexdocs.pm/elixir/Regex.html)
