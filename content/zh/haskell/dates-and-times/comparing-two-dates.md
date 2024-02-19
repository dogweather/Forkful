---
aliases:
- /zh/haskell/comparing-two-dates/
date: 2024-01-20 17:33:18.163721-07:00
description: "\u5728\u7F16\u7A0B\u4E2D\uFF0C\u6BD4\u8F83\u4E24\u4E2A\u65E5\u671F\u5C31\
  \u662F\u786E\u5B9A\u5B83\u4EEC\u7684\u5148\u540E\u987A\u5E8F\u3002\u7A0B\u5E8F\u5458\
  \u8FD9\u6837\u505A\u901A\u5E38\u662F\u4E3A\u4E86\u6392\u5E8F\u4E8B\u4EF6\u3001\u8BA1\
  \u7B97\u65F6\u95F4\u5DEE\u6216\u9A8C\u8BC1\u65F6\u95F4\u903B\u8F91\u3002"
isCJKLanguage: true
lastmod: 2024-02-18 23:08:59.189278
model: gpt-4-1106-preview
summary: "\u5728\u7F16\u7A0B\u4E2D\uFF0C\u6BD4\u8F83\u4E24\u4E2A\u65E5\u671F\u5C31\
  \u662F\u786E\u5B9A\u5B83\u4EEC\u7684\u5148\u540E\u987A\u5E8F\u3002\u7A0B\u5E8F\u5458\
  \u8FD9\u6837\u505A\u901A\u5E38\u662F\u4E3A\u4E86\u6392\u5E8F\u4E8B\u4EF6\u3001\u8BA1\
  \u7B97\u65F6\u95F4\u5DEE\u6216\u9A8C\u8BC1\u65F6\u95F4\u903B\u8F91\u3002"
title: "\u6BD4\u8F83\u4E24\u4E2A\u65E5\u671F"
---

{{< edit_this_page >}}

## What & Why? (是什么 & 为什么？)
在编程中，比较两个日期就是确定它们的先后顺序。程序员这样做通常是为了排序事件、计算时间差或验证时间逻辑。

## How to: (如何操作：)
在Haskell中，你可以使用`Data.Time`库来比较日期。这里有个例子：

```Haskell
import Data.Time

main :: IO ()
main = do
  let date1 = fromGregorian 2023 3 25 -- 2023年3月25日
  let date2 = fromGregorian 2023 4 1  -- 2023年4月1日
  print $ date1 < date2  -- 检查date1是否早于date2
  print $ date1 > date2  -- 检查date1是否晚于date2
  print $ date1 == date2 -- 检查date1和date2是否相同
```

输出结果将是：

```
True
False
False
```

## Deep Dive (深入了解)
在Haskell中，`Data.Time`是处理日期和时间的标准库。2006年引入，如今这个库是开发者处理日期常用的选择。虽然还有其他库如`time-recurrence`来处理重复事件，`Data.Time`仍然是最常用的。

`Data.Time`内部，日期比较用的是标准的比较运算符，因为`Data.Time.Calendar`里面的`Day`类型派生了`Eq`和`Ord`类。这就意味着你可以用`==`来检查是否相等，用`<`，`>`，`<=`，`>=`等来比较顺序。

值得注意的是，时区和夏令时可能会让比较复杂化。`Data.Time`也提供了处理时区的功能，但你得确保都把日期转化到相同的时区里比较才行。

## See Also (参考链接)
- Haskell `Data.Time`库文档：[https://hackage.haskell.org/package/time-1.12/docs/Data-Time.html](https://hackage.haskell.org/package/time-1.12/docs/Data-Time.html)
- 关于`Data.Time.Calendar`的更多信息：[https://hackage.haskell.org/package/time-1.12/docs/Data-Time-Calendar.html](https://hackage.haskell.org/package/time-1.12/docs/Data-Time-Calendar.html)
