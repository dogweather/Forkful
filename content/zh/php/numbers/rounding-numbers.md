---
title:                "数字取整"
aliases:
- /zh/php/rounding-numbers/
date:                  2024-01-26T03:46:07.457265-07:00
model:                 gpt-4-0125-preview
simple_title:         "数字取整"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/php/rounding-numbers.md"
---

{{< edit_this_page >}}

## 什么与为什么？
四舍五入意味着将数字截断到设定的精度，往往是到整数。程序员进行四舍五入是为了简化计算、提高性能或使输出对用户友好。

## 如何实现：
PHP提供了几种四舍五入数字的方法：`round()`、`ceil()` 和 `floor()`。以下是它们的工作方式：

```php
echo round(3.14159);   // 返回 3
echo round(3.14159, 2); // 返回 3.14

echo ceil(3.14159);    // 总是向上取整，返回 4

echo floor(3.14159);   // 总是向下取整，返回 3
```

## 深入探索
自古以来，在数学和计算中四舍五入数字一直是处理无限小数不切实际问题的重要手段。在PHP中，`round()`可以添加精度参数和模式， 影响其行为 - `PHP_ROUND_HALF_UP`、`PHP_ROUND_HALF_DOWN` 等，定义了当遇到 ".5" 情况时它的行为方式。精度在金融应用中至关重要，其中四舍五入可能受到法律规制，影响`round()`在代码中的实现方式。

除内置函数外，替代方案包括自定义四舍五入方法或BC Math函数，用于任意精度算术，这对需要更多控制的场景或处理非常大的数字（其中原生精度可能会失败）非常有用。

## 另请参阅
在PHP手册中了解更多：
- [PHP `round` 函数](https://php.net/manual/en/function.round.php)
- [PHP `ceil` 函数](https://php.net/manual/en/function.ceil.php)
- [PHP `floor` 函数](https://php.net/manual/en/function.floor.php)
- [BC Math 用于任意精度算术](https://php.net/manual/en/book.bc.php)
