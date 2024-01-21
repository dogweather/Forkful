---
title:                "比较两个日期"
date:                  2024-01-20T17:32:44.435092-07:00
model:                 gpt-4-1106-preview
simple_title:         "比较两个日期"
programming_language: "Elm"
category:             "Elm"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/elm/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why? 为什么以及为什么？
比较两个日期就是看哪个早、哪个晚或它们是否相同。程序员这么做通常是为了排序、验证或跟踪时间流。

## How to: 如何操作
```Elm
import Time exposing (Posix)
import Date

-- 假定有两个Posix时间戳
date1 : Posix
date1 = Time.millisToPosix 1588291200000  -- 2020年5月1日

date2 : Posix
date2 = Time.millisToPosix 1609459200000  -- 2021年1月1日

-- 比较函数
isBefore : Posix -> Posix -> Bool
isBefore = Time.compare < 0

isAfter : Posix -> Posix -> Bool
isAfter = Time.compare > 0

isEqualTo : Posix -> Posix -> Bool
isEqualTo = Time.compare == 0

-- 输出比较结果
compareDates : String
compareDates =
    if isBefore date1 date2 then
        "date1 is before date2"
    else if isAfter date1 date2 then
        "date1 is after date2"
    else if isEqualTo date1 date2 then
        "date1 is equal to date2"
    else
        "Can't compare the dates"

-- 检验
compareDates  -- 返回 "date1 is before date2"

```
## Deep Dive 深入了解
历史上，Elm处理时间一直在演变，现在用`Time.Posix`来代表时间点，这是个跨时区的通用表示。有多种方法比较日期，例如直接比较时间戳、转换为日历日期再比较，或者用库函数。这些方法各有利弊：直接比较时间戳快且简单，但不直观；转换成日历日期比较更容易理解，但需要更多代码；而库函数则介于两者之间。Elm社区提供的`elm-time`库就是这样的资源之一，它简化了日期比较等常见任务。

## See Also 另请参阅
- Elm Time: [https://package.elm-lang.org/packages/elm/time/latest/](https://package.elm-lang.org/packages/elm/time/latest/)
- Elm语言官方指南: [https://guide.elm-lang.org/](https://guide.elm-lang.org/)