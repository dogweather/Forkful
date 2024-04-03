---
date: 2024-01-20 17:39:13.941580-07:00
description: "\u5C06\u5B57\u7B26\u4E32\u8F6C\u6362\u4E3A\u5C0F\u5199\u610F\u5473\u7740\
  \u628A\u6240\u6709\u5927\u5199\u5B57\u6BCD\u6539\u4E3A\u5C0F\u5199\u5F62\u5F0F\u3002\
  \u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u6765\u7EDF\u4E00\u6570\u636E\u683C\u5F0F\u3001\
  \u63D0\u9AD8\u6BD4\u8F83\u6570\u636E\u65F6\u7684\u51C6\u786E\u6027\uFF0C\u6216\u662F\
  \u6EE1\u8DB3\u7279\u5B9A\u7F16\u7A0B\u8981\u6C42\u3002"
isCJKLanguage: true
lastmod: '2024-03-13T22:44:47.849124-06:00'
model: gpt-4-1106-preview
summary: "\u5C06\u5B57\u7B26\u4E32\u8F6C\u6362\u4E3A\u5C0F\u5199\u610F\u5473\u7740\
  \u628A\u6240\u6709\u5927\u5199\u5B57\u6BCD\u6539\u4E3A\u5C0F\u5199\u5F62\u5F0F\u3002\
  \u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u6765\u7EDF\u4E00\u6570\u636E\u683C\u5F0F\u3001\
  \u63D0\u9AD8\u6BD4\u8F83\u6570\u636E\u65F6\u7684\u51C6\u786E\u6027\uFF0C\u6216\u662F\
  \u6EE1\u8DB3\u7279\u5B9A\u7F16\u7A0B\u8981\u6C42\u3002."
title: "\u5C06\u5B57\u7B26\u4E32\u8F6C\u6362\u4E3A\u5C0F\u5199"
weight: 4
---

## How to: (如何操作：)
PHP 转换字符串为小写可以用 `strtolower()` 函数。给你看几个简单的例子：

```PHP
<?php
$exampleText = "Hello, World!";
echo strtolower($exampleText); // 输出: hello, world!

// 使用 UTF-8 字符
$chineseText = "PHP编程!";
echo strtolower($chineseText); // 输出依赖于具体环境和字符集配置
?>
```
注意：非英文字符的结果可能依赖于你的环境和字符集配置。

## Deep Dive (深入了解)
在历史上，字符串的大小写转换起初只适用于英文字符。随着编程国际化，`strtolower()` 函数通过 `locale` 设置支持多种语言，不过效果不总是理想。备选方案如 `mb_strtolower()` 用于多字节字符串，对 UTF-8 等编码更友好。

```PHP
// 使用多字节字符串函数
$exampleText = "Привет мир!";
echo mb_strtolower($exampleText, 'UTF-8'); // 输出: привет мир!
```

在 PHP 内部，`strtolower()` 和 `mb_strtolower()` 实现不同。`strtolower()` 逐字符处理，速度快但在非单字节字符集可能出错。`mb_strtolower()` 考虑了字符编码，兼容性更好，适用范围更广。

## See Also (另请参阅)
- PHP 官方文档中的 `strtolower()`：[https://www.php.net/manual/en/function.strtolower.php](https://www.php.net/manual/en/function.strtolower.php)
- PHP 官方文档中的 `mb_strtolower()`：[https://www.php.net/manual/en/function.mb-strtolower.php](https://www.php.net/manual/en/function.mb-strtolower.php)
- UTF-8 和字符编码基础：[https://www.php.net/manual/en/book.mbstring.php](https://www.php.net/manual/en/book.mbstring.php)
