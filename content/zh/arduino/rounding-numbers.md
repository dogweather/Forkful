---
title:                "数字取整"
date:                  2024-01-26T03:43:00.688474-07:00
model:                 gpt-4-0125-preview
simple_title:         "数字取整"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/arduino/rounding-numbers.md"
---

{{< edit_this_page >}}

## 什么以及为什么？
对数字进行四舍五入是将小数修整为最接近的整数值，或者设定的小数位数。程序员四舍五入数字，是为了使它们更易于阅读和处理，特别是在超出某一点的精确度不必要或可能导致错误时。

## 如何操作：
在Arduino中，您可以使用内置函数对数字进行四舍五入。关键角色有`round`，`ceil`和`floor`。这里有一个快速演示：

```arduino
void setup() {
  Serial.begin(9600);
  
  float myNumber = 123.4567;

  // 四舍五入到最近的整数
  Serial.println(round(myNumber)); // 输出: 123

  // 总是向上取整
  Serial.println(ceil(myNumber));  // 输出: 124

  // 总是向下取整
  Serial.println(floor(myNumber)); // 输出: 123
}

void loop() {
  // 没有东西可以循环。
}
```

## 深入探讨：
四舍五入算法有着悠久的历史；在数字电脑出现之前，它们就存在了。在模拟计算中，四舍五入是一个物理过程。在数字计算中，它是一个数学过程。

当我们从精度更高的类型（如`float`或`double`）转换为精度更低的类型（如`int`）时，需要四舍五入。但是我们如何四舍五入可以有所不同：

1. `round()`: 标准四舍五入。如果小数点是0.5或更高，就向上取；否则，就向下取。
2. `ceil()`: "ceiling"的简写，总是向上取整到最近的整数，即使它更靠近较低的数字。
3. `floor()`: 与ceiling相反; 总是向下取整。

在选择这些函数时，取决于四舍五入的值用途。测量可能需要标准四舍五入，金钱经常使用`floor`，而库存系统可能使用`ceil`，以确保一切都被计算在内。

Arduino对这些函数的实现很直接；它们不处理像四舍五入到特定小数位这样的额外情况。对于这种情况，需要自定义函数或更深入的数学操作——想想乘以某个数以移动小数点，四舍五入，然后除以同一个数。

四舍五入误差可能会累积，对长时间计算或迭代过程产生显著影响。程序员在对四舍五入的值执行多次操作时需要小心谨慎。

## 另见：
2. 对四舍五入的陷阱和策略进行深入探讨：[浮点数指南](https://floating-point-gui.de/)
3. 对于高级技巧，包括自定义四舍五入函数和处理四舍五入误差，您可能需要查阅学术资源或详细的编程指南。
