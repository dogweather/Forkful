---
title:                "日志记录"
aliases:
- zh/bash/logging.md
date:                  2024-01-26T00:59:23.509964-07:00
model:                 gpt-4-1106-preview
simple_title:         "日志记录"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/bash/logging.md"
---

{{< edit_this_page >}}

## 什么 & 为什么？

日志记录是将程序运行过程中的事件、错误和其他重要信息记录到文件或输出流中的做法。程序员这么做是为了追踪他们的应用程序的行为、调试问题以及保持操作的历史记录，这可以帮助未来的故障排除。

## 如何操作：

在 Bash 中，日志记录可以简单到将输出重定向或追加到文件中。这里有一个基础的示例：

```Bash
echo "开始执行脚本..." >> script.log
# 你的脚本命令在这里
echo "脚本在 $(date) 完成" >> script.log
```

如果你想要更高级的功能，你可以整合 syslog 来进行系统级的日志记录：

```Bash
logger "我脚本的自定义信息"
```

`logger` 将日志信息发送给 syslog 服务，然后 syslog 根据系统的 syslog 配置来处理这个信息。

在 `script.log` 中捕获的样本输出：

```Bash
开始执行脚本...
脚本在 Tue Mar 23 09:26:35 PDT 2021 完成
```

## 深入探讨

历史上在类 Unix 系统中，syslog 服务便促进了日志记录，允许不同的应用程序和系统的部分中心化地记录消息。这允许在系统中实现一种标准化的日志记录机制。

当考虑替代方案时，一些人可能会考虑使用 `syslog-ng` 或者 `rsyslog` 来获取更先进的日志记录功能，或者将日志写入时序数据库以进行分析目的。对于复杂程度较高的应用程序，使用专门的日志记录库或应用程序，比如 Java 生态中的 Log4j 或者 PHP 中的 Monolog，这些可以提供结构化和可配置的日志记录选项，即使对于像 Bash 这样的脚本语言来说也是有意义的。

你实现日志记录的方式极大地取决于你的应用程序的需求。如果你只是需要简单的输出来跟踪脚本进度，追加消息到文件是简单且方便的。然而，对于更可扩展和健壮的日志记录，你会想要整合一个支持日志轮转、日志级别和远程日志记录等功能的日志系统。

## 另请参阅

- `logger` 和 `syslog` 函数的 `man` 页面总是你的好帮手，尝试 `man logger` 或 `man syslog`。
- 对于系统日志记录的深入了解，可以考虑阅读 `rsyslog` 和 `syslog-ng` 文档。
- 要了解关于在类 Unix 系统中日志记录的历史背景和原则，RFC 5424 中记录的 `Syslog` 协议提供了全面的信息。
