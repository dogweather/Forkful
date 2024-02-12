---
title:                "字符串插值"
date:                  2024-01-20T17:50:01.834015-07:00
model:                 gpt-4-1106-preview
simple_title:         "字符串插值"

tag:                  "Strings"
isCJKLanguage:        true
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/arduino/interpolating-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (是什么？为什么？)
字符串插值指把变量嵌入字符串中的操作。程序员这么做是为了简化字符串构建和提高代码可读性。

## How to (如何操作)：
Arduino本身没有内置的字符串插值功能，但你可以通过串联（concatenation）和占位符的方式达到类似的效果。以下是示例代码：

```Arduino
void setup() {
  // 开始串口通信
  Serial.begin(9600);

  // 定义变量
  int temperature = 26;
  String message = "室温是： " + String(temperature) + "°C";

  // 打印到串口监视器
  Serial.println(message);
}

void loop() {
  // 不需要重复执行操作，loop留空
}
```
输出:
```
室温是： 26°C
```

## Deep Dive (深入探讨):
过去，Arduino程序中使用字符串的时候，我们依赖字符数组和函数比如`sprintf()`来创建复杂的字符串。这些方法效率高，但不易于新手理解。现代Arduino编程支持`String`对象，虽然它消耗内存多，但简化了字符串的处理。

有些高级语言如Python和JavaScript内置了字符串插值功能。虽然Arduino C++没有这个功能，但你仍可以利用`String`类和字符数组灵活地构建字符串。

在复杂项目中，仍然推荐使用字符数组和标准C函数，因为它们对内存管理更友好，尤其是在资源有限的微控制器上。

## See Also (另见)：
- [Arduino String Reference](https://www.arduino.cc/reference/en/language/variables/data-types/string/)
- [Arduino String Concatenation](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/concat/)
- [C++ sprintf()](http://www.cplusplus.com/reference/cstdio/sprintf/)
