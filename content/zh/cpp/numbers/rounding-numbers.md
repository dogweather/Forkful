---
date: 2024-01-26 03:44:39.958014-07:00
description: "\u6570\u5B57\u56DB\u820D\u4E94\u5165\u610F\u5473\u7740\u5C06\u4E00\u4E2A\
  \u503C\u8C03\u6574\u5230\u6700\u8FD1\u7684\u6574\u6570\u6216\u6307\u5B9A\u7684\u7CBE\
  \u5EA6\u3002\u5F00\u53D1\u4EBA\u5458\u8FDB\u884C\u56DB\u820D\u4E94\u5165\u64CD\u4F5C\
  \u662F\u4E3A\u4E86\u7B80\u5316\u3001\u7B26\u5408\u73B0\u5B9E\u4E16\u754C\u7684\u9650\
  \u5236\uFF0C\u6216\u901A\u8FC7\u4E22\u5F03\u591A\u4F59\u7684\u7CBE\u5EA6\u6765\u63D0\
  \u9AD8\u6027\u80FD\u3002"
lastmod: '2024-03-13T22:44:48.104812-06:00'
model: gpt-4-0125-preview
summary: "\u6570\u5B57\u56DB\u820D\u4E94\u5165\u610F\u5473\u7740\u5C06\u4E00\u4E2A\
  \u503C\u8C03\u6574\u5230\u6700\u8FD1\u7684\u6574\u6570\u6216\u6307\u5B9A\u7684\u7CBE\
  \u5EA6\u3002\u5F00\u53D1\u4EBA\u5458\u8FDB\u884C\u56DB\u820D\u4E94\u5165\u64CD\u4F5C\
  \u662F\u4E3A\u4E86\u7B80\u5316\u3001\u7B26\u5408\u73B0\u5B9E\u4E16\u754C\u7684\u9650\
  \u5236\uFF0C\u6216\u901A\u8FC7\u4E22\u5F03\u591A\u4F59\u7684\u7CBE\u5EA6\u6765\u63D0\
  \u9AD8\u6027\u80FD\u3002."
title: "\u6570\u5B57\u53D6\u6574"
weight: 13
---

## 如何实现：
C++提供了几种四舍五入数字的方法，比如`floor()`、`ceil()`和`round()`：

```C++
#include <iostream>
#include <cmath> // 用于四舍五入的函数

int main() {
    double num = 3.14;

    std::cout << "floor: " << std::floor(num) << "\n"; // 输出: floor: 3
    std::cout << "ceil: " << std::ceil(num) << "\n";   // 输出: ceil: 4
    std::cout << "round: " << std::round(num) << "\n"; // 输出: round: 3

    // 对于固定精度的四舍五入，例如四舍五入到两位小数：
    double precise_num = 3.146;
    double multiplier = 100.0;
    double rounded = std::round(precise_num * multiplier) / multiplier;

    std::cout << "四舍五入到两位小数: " << rounded << "\n"; // 输出: 四舍五入到两位小数: 3.15

    return 0;
}
```

## 深入了解
在C++11之前，四舍五入依赖于手工技术或非标准库。今天，`<cmath>`提供了健壮的方法。`floor()`向下取整，`ceil()`向上取整，而`round()`则取最近的整数，甚至处理平局（0.5的情况）时通过取偶数来四舍五入。

了解这些函数的行为至关重要；例如，负数可能会让你措手不及（`std::round(-2.5)` 产生 `-2.0`）。

有什么替代方案吗？对正数先加0.5然后转换为int是一个经典技巧，但它对负数不起作用，而且不适用于所有类型。像Boost这样的库可以提供更细微的方法，而语言扩展或编译器内置函数可以针对特定硬件进行优化。

## 另请参阅
- C++ `<cmath>`参考资料：https://en.cppreference.com/w/cpp/header/cmath
- 浮点算术的IEEE标准（IEEE 754）：https://ieeexplore.ieee.org/document/4610935
- Boost数值转换库：https://www.boost.org/doc/libs/release/libs/numeric/conversion/
