---
date: 2024-01-20 17:32:21.998867-07:00
description: "\u6BD4\u8F83\u4E24\u4E2A\u65E5\u671F\u610F\u5473\u7740\u67E5\u770B\u5B83\
  \u4EEC\u662F\u5426\u76F8\u540C\uFF0C\u6216\u8005\u4E00\u4E2A\u662F\u5426\u5728\u53E6\
  \u4E00\u4E2A\u4E4B\u524D\u6216\u4E4B\u540E\u3002\u7A0B\u5E8F\u5458\u8FD9\u4E48\u505A\
  \u662F\u4E3A\u4E86\u5904\u7406\u65E5\u5386\u4E8B\u4EF6\u3001\u76D1\u63A7\u65F6\u95F4\
  \u95F4\u9694\u6216\u9A8C\u8BC1\u6709\u6548\u671F\u9650\u7B49\u3002"
isCJKLanguage: true
lastmod: '2024-03-13T22:44:48.076356-06:00'
model: gpt-4-1106-preview
summary: "\u6BD4\u8F83\u4E24\u4E2A\u65E5\u671F\u610F\u5473\u7740\u67E5\u770B\u5B83\
  \u4EEC\u662F\u5426\u76F8\u540C\uFF0C\u6216\u8005\u4E00\u4E2A\u662F\u5426\u5728\u53E6\
  \u4E00\u4E2A\u4E4B\u524D\u6216\u4E4B\u540E\u3002\u7A0B\u5E8F\u5458\u8FD9\u4E48\u505A\
  \u662F\u4E3A\u4E86\u5904\u7406\u65E5\u5386\u4E8B\u4EF6\u3001\u76D1\u63A7\u65F6\u95F4\
  \u95F4\u9694\u6216\u9A8C\u8BC1\u6709\u6548\u671F\u9650\u7B49\u3002."
title: "\u6BD4\u8F83\u4E24\u4E2A\u65E5\u671F"
weight: 27
---

## How to: 怎么做？
```Arduino
#include <TimeLib.h>

void setup() {
  Serial.begin(9600);
  setTime(8, 29, 0, 5, 11, 2023); // 设置当前时间为 2023年11月5日 8:29:00
  time_t t1 = now(); // 获取当前时间

  setTime(9, 15, 0, 12, 1, 2024); // 设置另一个时间为 2024年1月12日 9:15:00
  time_t t2 = now(); // 获取设置的时间

  compareDates(t1, t2);
}

void loop() {
  // 主程序循环为空，因为我们不需要连续比较日期
}

void compareDates(time_t d1, time_t d2) {
  if(d1 > d2) {
    Serial.println("Date1 is after Date2");
  } else if(d1 < d2) {
    Serial.println("Date1 is before Date2");
  } else {
    Serial.println("Dates are equal");
  }
}
```
示例输出：
```
Date1 is before Date2
```

## Deep Dive: 深入了解
比较日期的需求促成了电脑历史中时间管理功能的发展。在没有内建时间功能的电脑硬件上，如早期的Arduino板，实时时钟（RTC）模块被用来跟踪实际时间。使用库如TimeLib，能简化日期比较的流程。

可选方法包括使用简单的整数比较，如上面的例子，或利用更复杂的时间库来处理闰年和时区等问题。在Arduino中，程序员通常会将时间以Unix时间戳格式（从1970年1月1日起算的秒数）来存储和比较，因为它简化了比较过程。

## See Also: 参考链接
- Arduino Time Library: https://www.arduino.cc/reference/en/libraries/time/
- DS3231 RTC Arduino Module (常用的RTC模块): https://www.arduino.cc/en/Guide/Libraries#toc4
- Unix Time and its importance in Programming: http://unixtimestamp.com/
