---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:55:19.229092-07:00
description: "\u5728 Google Apps \u811A\u672C\u4E2D\u4F7F\u7528\u5B57\u7B26\u4E32\u63D2\
  \u503C\u53EF\u4EE5\u52A8\u6001\u5730\u5C06\u8868\u8FBE\u5F0F\u5D4C\u5165\u5230\u5B57\
  \u7B26\u4E32\u4E2D\uFF0C\u6709\u52A9\u4E8E\u521B\u5EFA\u66F4\u53EF\u8BFB\u548C\u53EF\
  \u7EF4\u62A4\u7684\u4EE3\u7801\u3002\u7A0B\u5E8F\u5458\u5229\u7528\u8FD9\u79CD\u6280\
  \u672F\u65E0\u7F1D\u5730\u5C06\u53D8\u91CF\u548C\u8868\u8FBE\u5F0F\u96C6\u6210\u5230\
  \u5B57\u7B26\u4E32\u4E2D\uFF0C\u800C\u65E0\u9700\u7E41\u7410\u7684\u8FDE\u63A5\u8BED\
  \u6CD5\u3002"
lastmod: '2024-03-13T22:44:47.180971-06:00'
model: gpt-4-0125-preview
summary: "\u5728 Google Apps \u811A\u672C\u4E2D\u4F7F\u7528\u5B57\u7B26\u4E32\u63D2\
  \u503C\u53EF\u4EE5\u52A8\u6001\u5730\u5C06\u8868\u8FBE\u5F0F\u5D4C\u5165\u5230\u5B57\
  \u7B26\u4E32\u4E2D\uFF0C\u6709\u52A9\u4E8E\u521B\u5EFA\u66F4\u53EF\u8BFB\u548C\u53EF\
  \u7EF4\u62A4\u7684\u4EE3\u7801\u3002\u7A0B\u5E8F\u5458\u5229\u7528\u8FD9\u79CD\u6280\
  \u672F\u65E0\u7F1D\u5730\u5C06\u53D8\u91CF\u548C\u8868\u8FBE\u5F0F\u96C6\u6210\u5230\
  \u5B57\u7B26\u4E32\u4E2D\uFF0C\u800C\u65E0\u9700\u7E41\u7410\u7684\u8FDE\u63A5\u8BED\
  \u6CD5\u3002."
title: "\u5B57\u7B26\u4E32\u63D2\u503C"
weight: 8
---

## 如何操作:
在 Google Apps 脚本中，通过模板字面量（template literals）实现字符串插值。这些是允许嵌入表达式的字符串字面量，用反引号（\`）代替通常的引号表示。以下是使用它们的方式：

```javascript
// 一个基本示例
function basicInterpolationExample() {
  const user = 'Alice';
  console.log(`Hello, ${user}!`); // 输出：Hello, Alice!
}

// 使用表达式
function expressionInterpolationExample() {
  const a = 5;
  const b = 10;
  console.log(`Five plus ten is ${a + b}.`); // 输出：Five plus ten is 15.
}

// 多行字符串
function multiLineStringExample() {
  const item = 'Google Apps Script';
  console.log(`This is a multi-line string:
Hello all,
We are discussing ${item} today.`);
  // 输出：
  // This is a multi-line string:
  // Hello all,
  // We are discussing Google Apps Script today.
}

basicInterpolationExample();
expressionInterpolationExample();
multiLineStringExample();
```

这些示例展示了基本使用、嵌入表达式和使用插值创建多行字符串。

## 深入探讨
包括字符串插值在内的模板字面量在 ECMAScript 2015（ES6）中引入，并随后被 Google Apps 脚本采用。在此之前，程序员必须完全依赖字符串连接，对于复杂字符串或整合许多变量值时可能会变得笨拙。

```javascript
// 旧方式（ES6之前）
var user = 'Bob';
console.log('Hello, ' + user + '!');
```

虽然字符串插值是一个强大的功能，但在使用中需要注意上下文。例如，直接嵌入没有适当清洁的用户输入可能会导致安全问题，例如注入攻击。Google Apps 脚本开发者应确保任何动态内容插入到字符串中时都经过适当检查或清洁。

与其他编程语言相比，字符串插值的概念广泛存在，语法各异。Python 使用 f-string 或 `format` 方法，Ruby 在双引号字符串中使用 `#{}`，许多现代语言都因为它们提供的可读性和便利性而采纳了类似的功能。

尽管 Google Apps 脚本未提供超出 ECMAScript 标准提供的其他插值特性，但现有的功能强大且足以应对大多数使用情况。来自拥有更复杂插值机制语言的开发者可能需要调整他们的期望，但很可能会欣赏 Google Apps 脚本中模板字面量的简单性和效率。
