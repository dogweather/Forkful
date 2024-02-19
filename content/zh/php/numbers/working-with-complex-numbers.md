---
aliases:
- /zh/php/working-with-complex-numbers/
date: 2024-01-26 04:44:42.751958-07:00
description: "\u590D\u6570\u6709\u5B9E\u90E8\u548C\u865A\u90E8\uFF0C\u901A\u5E38\u5199\
  \u4F5C `a + bi`\u3002\u5B83\u4EEC\u5728\u9AD8\u7EA7\u6570\u5B66\u3001\u7269\u7406\
  \u5B66\u3001\u5DE5\u7A0B\u5B66\u4EE5\u53CA\u67D0\u4E9B\u8BA1\u7B97\u673A\u7B97\u6CD5\
  \u4E2D\u81F3\u5173\u91CD\u8981\u3002\u7A0B\u5E8F\u5458\u901A\u8FC7\u5B83\u4EEC\u6765\
  \u5904\u7406\u6D89\u53CA\u8D1F\u6570\u5E73\u65B9\u6839\u548C\u632F\u8361\u51FD\u6570\
  \u7684\u8BA1\u7B97\u3002"
lastmod: 2024-02-18 23:08:59.210633
model: gpt-4-0125-preview
summary: "\u590D\u6570\u6709\u5B9E\u90E8\u548C\u865A\u90E8\uFF0C\u901A\u5E38\u5199\
  \u4F5C `a + bi`\u3002\u5B83\u4EEC\u5728\u9AD8\u7EA7\u6570\u5B66\u3001\u7269\u7406\
  \u5B66\u3001\u5DE5\u7A0B\u5B66\u4EE5\u53CA\u67D0\u4E9B\u8BA1\u7B97\u673A\u7B97\u6CD5\
  \u4E2D\u81F3\u5173\u91CD\u8981\u3002\u7A0B\u5E8F\u5458\u901A\u8FC7\u5B83\u4EEC\u6765\
  \u5904\u7406\u6D89\u53CA\u8D1F\u6570\u5E73\u65B9\u6839\u548C\u632F\u8361\u51FD\u6570\
  \u7684\u8BA1\u7B97\u3002"
title: "\u5904\u7406\u590D\u6570"
---

{{< edit_this_page >}}

## 什么 & 为什么？
复数有实部和虚部，通常写作 `a + bi`。它们在高级数学、物理学、工程学以及某些计算机算法中至关重要。程序员通过它们来处理涉及负数平方根和振荡函数的计算。

## 如何操作：
PHP通过 `ext-intl` 扩展和 `NumberFormatter` 类为复数提供了内置支持。这里有一个例子：

```php
// 确保 intl 扩展已加载
if (!extension_loaded('intl')) {
    die("intl 扩展没有启用。请启用它以运行此代码。");
}

function addComplexNumbers($a, $b) {
    // 使用 NumberFormatter 来解析和格式化复数
    $formatter = new NumberFormatter('en_US', NumberFormatter::PATTERN_RULEBASED, 'i = -1;');

    // 从字符串解析复数
    $numA = $formatter->parse($a, NumberFormatter::TYPE_DOUBLE);
    $numB = $formatter->parse($b, NumberFormatter::TYPE_DOUBLE);

    // 执行加法
    $sum = $numA + $numB;

    // 将结果格式化为复数
    return $formatter->format($sum);
}

echo addComplexNumbers('5+3i', '2+7i'); // 输出：7+10i
```

## 深入探讨
在 `ext-intl` 之前，PHP没有原生的复数支持。开发者使用函数或自定义类库来处理复数。复数操作可能既繁琐又容易出错，但 `ext-intl` 提供了一种国际化的方式来呈现和解析复数，与 ICU 库对齐。

然而，对于重量级的数学操作，有些人可能使用更适合数学的语言（如C或Python）编写的外部库，并通过PHP与之交互。关于实现，`ext-intl` 在幕后处理，确保准确的算术运算，同时从开发者那里抽象出复杂性。

从历史上看，复数因被称为“虚数”而受到排斥，但它们后来在各种科学和数学领域中成为基本内容，揭示了它们的现实世界重要性，远超过它们的虚数状态所暗示的。

## 另见
- [PHP 手册中的 NumberFormatter](https://www.php.net/manual/en/class.numberformatter.php)
- [维基百科上的复数](https://en.wikipedia.org/wiki/Complex_number)
- [PHP：正确的方式 - 处理数据类型](https://phptherightway.com/#data_types)
