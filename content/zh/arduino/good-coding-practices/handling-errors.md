---
aliases:
- /zh/arduino/handling-errors/
date: 2024-01-26 00:36:46.803138-07:00
description: "\u5728\u60A8\u7684\u7A0B\u5E8F\u4E2D\u5904\u7406\u9519\u8BEF\u53EF\u4EE5\
  \u6293\u4F4F\u90A3\u4E9B\u672A\u9884\u89C1\u5230\u7684\u3001\u53EF\u80FD\u4F1A\u8BA9\
  \u60A8\u72AF\u9519\u7684\u4E8B\u60C5\u3002\u5F53\u51FA\u73B0\u610F\u6599\u4E4B\u5916\
  \u7684\u60C5\u51B5\u65F6\uFF0C\u901A\u8FC7\u8FD9\u6837\u505A\u53EF\u4EE5\u9632\u6B62\
  \u60A8\u7684Arduino\u53D1\u751F\u6545\u969C\u3002"
lastmod: 2024-02-18 23:08:59.375197
model: gpt-4-1106-preview
summary: "\u5728\u60A8\u7684\u7A0B\u5E8F\u4E2D\u5904\u7406\u9519\u8BEF\u53EF\u4EE5\
  \u6293\u4F4F\u90A3\u4E9B\u672A\u9884\u89C1\u5230\u7684\u3001\u53EF\u80FD\u4F1A\u8BA9\
  \u60A8\u72AF\u9519\u7684\u4E8B\u60C5\u3002\u5F53\u51FA\u73B0\u610F\u6599\u4E4B\u5916\
  \u7684\u60C5\u51B5\u65F6\uFF0C\u901A\u8FC7\u8FD9\u6837\u505A\u53EF\u4EE5\u9632\u6B62\
  \u60A8\u7684Arduino\u53D1\u751F\u6545\u969C\u3002"
title: "\u5904\u7406\u9519\u8BEF"
---

{{< edit_this_page >}}

## 是什么以及为什么？

在您的程序中处理错误可以抓住那些未预见到的、可能会让您犯错的事情。当出现意料之外的情况时，通过这样做可以防止您的Arduino发生故障。

## 如何操作：

比方说，您的Arduino正在读取一个偶尔可能产生超出范围值的传感器。以下是您可能如何处理这个问题：

```Arduino
int sensorValue = analogRead(A0);

if (sensorValue >= 0 && sensorValue <= 1023) {
  // 值在范围之内，继续处理
  Serial.println(sensorValue);
} else {
  // 值超出范围，处理错误
  Serial.println("错误：传感器值超出范围。");
}
```
示例输出：
```
523
错误：传感器值超出范围。
761
```

## 深入探讨

错误处理并不总是这么直截了当。在早期，开发人员常常忽略错误，导致令人畏惧的“未定义行为”。随着编程的发展，工具也在进化 — 现在许多语言中都有异常处理，但由于硬件限制和C++的根源，在Arduino世界中仍然是传统的“先检查”的做法。

在Arduino编程中，您经常会看到用`if-else`语句进行错误处理。但还有其他选择：使用`assert`函数在条件失败时停止执行，或在硬件设置本身中设计故障安全机制。

在实现错误处理时，考虑停止程序与允许它继续运行并采取默认或安全状态之间的影响。这是一种权衡，正确的选择取决于中断的潜在危害与错误操作的潜在危害。

## 另请参阅

用以下资源来提高您对错误检测和处理的了解：

- Arduino语言参考：https://www.arduino.cc/reference/en/
- Embedded Artistry更深入地探讨错误处理：https://embeddedartistry.com/blog/2017/05/17/creating-a-circular-buffer-in-c-and-c/
- C++错误处理：https://en.cppreference.com/w/cpp/error/exception

这应该能够让您具备规避Arduino冒险中错误陷阱的知识和信心。
