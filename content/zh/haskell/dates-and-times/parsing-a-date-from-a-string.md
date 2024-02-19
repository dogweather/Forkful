---
aliases:
- /zh/haskell/parsing-a-date-from-a-string/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:20.397082-07:00
description: "\u5728Haskell\u4E2D\u89E3\u6790\u5B57\u7B26\u4E32\u4E2D\u7684\u65E5\u671F\
  \u6D89\u53CA\u5C06\u65E5\u671F\u7684\u6587\u672C\u8868\u793A\u5F62\u5F0F\u8F6C\u6362\
  \u4E3A\u7A0B\u5E8F\u53EF\u4EE5\u64CD\u4F5C\u7684\u7ED3\u6784\u5316\u683C\u5F0F\u3002\
  \u8FD9\u4E2A\u8FC7\u7A0B\u5BF9\u4E8E\u5904\u7406\u65E5\u5386\u6570\u636E\u7684\u5E94\
  \u7528\u7A0B\u5E8F\u81F3\u5173\u91CD\u8981\uFF0C\u4F7F\u5F97\u8BA1\u7B97\u6301\u7EED\
  \u65F6\u95F4\u3001\u8C03\u5EA6\u548C\u6570\u636E\u9A8C\u8BC1\u7B49\u529F\u80FD\u6210\
  \u4E3A\u53EF\u80FD\u3002"
lastmod: 2024-02-18 23:08:59.182483
model: gpt-4-0125-preview
summary: "\u5728Haskell\u4E2D\u89E3\u6790\u5B57\u7B26\u4E32\u4E2D\u7684\u65E5\u671F\
  \u6D89\u53CA\u5C06\u65E5\u671F\u7684\u6587\u672C\u8868\u793A\u5F62\u5F0F\u8F6C\u6362\
  \u4E3A\u7A0B\u5E8F\u53EF\u4EE5\u64CD\u4F5C\u7684\u7ED3\u6784\u5316\u683C\u5F0F\u3002\
  \u8FD9\u4E2A\u8FC7\u7A0B\u5BF9\u4E8E\u5904\u7406\u65E5\u5386\u6570\u636E\u7684\u5E94\
  \u7528\u7A0B\u5E8F\u81F3\u5173\u91CD\u8981\uFF0C\u4F7F\u5F97\u8BA1\u7B97\u6301\u7EED\
  \u65F6\u95F4\u3001\u8C03\u5EA6\u548C\u6570\u636E\u9A8C\u8BC1\u7B49\u529F\u80FD\u6210\
  \u4E3A\u53EF\u80FD\u3002"
title: "\u4ECE\u5B57\u7B26\u4E32\u89E3\u6790\u65E5\u671F"
---

{{< edit_this_page >}}

## 什么 & 为什么?

在Haskell中解析字符串中的日期涉及将日期的文本表示形式转换为程序可以操作的结构化格式。这个过程对于处理日历数据的应用程序至关重要，使得计算持续时间、调度和数据验证等功能成为可能。

## 如何操作：

开箱即用的Haskell为解析日期提供了基本工具，但利用像`time`这样的库来获取核心功能和`date-parse`或`time-parse`这样的库来实现更灵活的解析，可以显著简化任务。

首先，确保你有`time`库可用；它通常包含在GHC中，但如果需要将其指定为依赖项，请将`time`添加到项目的cabal文件中，或使用`cabal install time`手动安装它。

```haskell
import Data.Time.Format
import Data.Time.Clock
import System.Locale (defaultTimeLocale)

-- 使用time库以标准格式解析日期
parseBasicDate :: String -> Maybe UTCTime
parseBasicDate = parseTimeM True defaultTimeLocale "%Y-%m-%d" 
```

示例使用和输出：

```haskell
main :: IO ()
main = print $ parseBasicDate "2023-04-01"

-- 输出：Just 2023-03-31 22:00:00 UTC
```

对于需要处理多种格式或地区的更复杂场景，第三方库如`date-parse`可能更加方便：

假设你已将`date-parse`添加到你的依赖项并安装了它，以下是你可能使用它的方式：

```haskell
import Data.Time.Calendar
import Text.Date.Parse (parseDate)

-- 使用date-parse库解析日期字符串支持多种格式
parseFlexibleDate :: String -> Maybe Day
parseFlexibleDate = parseDate
```

使用`date-parse`的示例：

```haskell
main :: IO ()
main = print $ parseFlexibleDate "April 1, 2023"

-- 输出：Just 2023-04-01
```

每个示例都演示了如何将字符串转换为Haskell中可用的日期对象的基本方法。在使用`time`库的内置函数和选择像`date-parse`这样的第三方解决方案之间的选择，取决于你的应用程序的特定需求，如你需要处理的输入格式的范围。
