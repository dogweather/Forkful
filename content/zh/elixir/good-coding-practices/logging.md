---
date: 2024-01-26 01:02:35.692046-07:00
description: "\u5728\u8F6F\u4EF6\u5F00\u53D1\u4E2D\uFF0C\u65E5\u5FD7\u8BB0\u5F55\u662F\
  \u6307\u5728\u7A0B\u5E8F\u8FD0\u884C\u65F6\u8BB0\u5F55\u53D1\u751F\u7684\u4E8B\u4EF6\
  \u7684\u6280\u672F\uFF0C\u901A\u5E38\u8BB0\u5F55\u5230\u6587\u4EF6\u6216\u5916\u90E8\
  \u7CFB\u7EDF\u4E2D\u3002\u7A0B\u5E8F\u5458\u8FD9\u4E48\u505A\u662F\u4E3A\u4E86\u83B7\
  \u53D6\u8F6F\u4EF6\u884C\u4E3A\u7684\u6D1E\u5BDF\u3001\u6392\u9664\u6545\u969C\uFF0C\
  \u5E76\u4E14\u7EF4\u62A4\u64CD\u4F5C\u5386\u53F2\u8BB0\u5F55\uFF0C\u8FD9\u5BF9\u4E8E\
  \u8C03\u8BD5\u548C\u76D1\u63A7\u5E94\u7528\u7A0B\u5E8F\u7684\u5065\u5EB7\u81F3\u5173\
  \u91CD\u8981\u3002"
lastmod: '2024-03-13T22:44:47.373078-06:00'
model: gpt-4-1106-preview
summary: "\u5728\u8F6F\u4EF6\u5F00\u53D1\u4E2D\uFF0C\u65E5\u5FD7\u8BB0\u5F55\u662F\
  \u6307\u5728\u7A0B\u5E8F\u8FD0\u884C\u65F6\u8BB0\u5F55\u53D1\u751F\u7684\u4E8B\u4EF6\
  \u7684\u6280\u672F\uFF0C\u901A\u5E38\u8BB0\u5F55\u5230\u6587\u4EF6\u6216\u5916\u90E8\
  \u7CFB\u7EDF\u4E2D\u3002\u7A0B\u5E8F\u5458\u8FD9\u4E48\u505A\u662F\u4E3A\u4E86\u83B7\
  \u53D6\u8F6F\u4EF6\u884C\u4E3A\u7684\u6D1E\u5BDF\u3001\u6392\u9664\u6545\u969C\uFF0C\
  \u5E76\u4E14\u7EF4\u62A4\u64CD\u4F5C\u5386\u53F2\u8BB0\u5F55\uFF0C\u8FD9\u5BF9\u4E8E\
  \u8C03\u8BD5\u548C\u76D1\u63A7\u5E94\u7528\u7A0B\u5E8F\u7684\u5065\u5EB7\u81F3\u5173\
  \u91CD\u8981\u3002."
title: "\u65E5\u5FD7\u8BB0\u5F55"
weight: 17
---

## 如何操作：
在Elixir中，记录信息的主要方式是通过内置的`Logger`模块。以下是使用它的方法：

```elixir
defmodule MyApplication do
  require Logger

  def do_something_important(param) do
    Logger.info("开始重要进程，参数为：#{param}")

    # 模拟正在完成的工作
    :timer.sleep(1000)

    Logger.debug("进程完成。")
  rescue
    error -> Logger.error("发生错误：#{inspect(error)}")
  end
end

# 要查看日志，你只需调用该函数：
MyApplication.do_something_important("MyParam")
```

这个简单的片段展示了如何以不同的级别记录日志（`info`，`debug`和`error`）。当你运行它时，除非你将Logger级别配置为`:debug`，否则你不会看到调试消息。默认情况下，Elixir的Logger会过滤掉级别低于`info`的日志消息。

在`:info`级别下的示例输出可能如下所示：
```
14:32:40.123 [info]  开始重要进程，参数为：MyParam
14:32:41.126 [error] 发生错误：％RuntimeError{message: "运行时错误"}
```

## 深入探讨：
Elixir的`Logger`是内置工具，自该语言初期就是其部分组成。它受其他BEAM语言如Erlang的日志系统影响。Logger提供了不同级别的日志记录 - `:debug`，`:info`，`:warn`和`:error` - 并且它是可插拔的，允许不同的后端挂接以处理日志消息。

对于更复杂的场景，一个内置Logger的替代品是使用如`Logstash`或`Sentry`这样的Elixir日志库，它们能提供额外的特性，如错误追踪和更直观格式的聚合。对于本地开发，Elixir开发人员常依赖内置Logger的功能，因为它简单且与BEAM VM集成。

在底层，Logger模块提供了异步和同步日志记录。默认的是异步日志记录，它不会在记录消息时阻塞你的应用程序执行。这确保了日志记录不会对性能产生负面影响。然而，在你需要保证消息按发送顺序记录时，可以启用同步日志记录。

可以在Elixir应用程序的`config/config.exs`文件中调整Logger配置，你可以设置日志级别、格式、元数据等。始终记得为不同的环境调整你的日志级别和输出；你不会希望冗长的调试日志充斥你的生产系统。

## 参见：
- 官方Elixir Logger文档：https://hexdocs.pm/logger/Logger.html
- 关于Elixir日志记录最佳实践的博客文章：https://blog.appsignal.com/2020/05/06/elixir-logging-tips-and-tricks.html
- Hex上的Sentry for Elixir：https://hex.pm/packages/sentry
- Elixir School对Logger的课程：https://elixirschool.com/en/lessons/specifics/debugging/#logging
