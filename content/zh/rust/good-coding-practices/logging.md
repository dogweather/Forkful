---
title:                "日志记录"
date:                  2024-01-26T01:09:07.650691-07:00
model:                 gpt-4-1106-preview
simple_title:         "日志记录"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/rust/logging.md"
---

{{< edit_this_page >}}

## 什么 & 为什么？

日志记录就像是为你的应用程序维护一个日记一样；它是记录运行时事件、错误和其他相关数据的实践。开发人员使用日志来诊断问题、监控系统行为，并收集促进改进的见解——这是运营智能的基本要素。

## 如何操作：

让我们在 Rust 中使用 `log` 库来设置一个基本的日志记录场景，它提供了一个日志记录外观（facade），以及 `env_logger`，一个为 `log` 库提供的日志记录实现。首先，将它们添加到你的 Cargo.toml 中：

```toml
[dependencies]
log = "0.4.14"
env_logger = "0.9.0"
```

现在，在你的 `main.rs` 中设置并初始化 logger：

```rust
use log::{info, warn};

fn main() {
    env_logger::init();

    info!("这是一条信息消息。");
    warn!("这是一条警告消息。");
}
```

使用 `RUST_LOG=info cargo run` 运行你的应用程序，你将看到输出：

```
INFO: 这是一条信息消息。
WARN: 这是一条警告消息。
```

通过将 `RUST_LOG` 环境变量设置为 `error`、`warn`、`info`、`debug` 或 `trace` 来控制你的日志的详细程度。

## 深入了解

日志记录的概念并不是什么新鲜事物；它自计算机早期以来就已存在。在软件中通用日志记录之前，开发人员依赖于诸如打印语句或调试器工具之类的原始方法来跟踪程序执行。随着程序变得更加复杂，对结构化日志记录方法的需求也随之增长。

在 Rust 中，`log` 库抽象了日志记录的实现细节，允许开发人员插入不同的日志后端。虽然 `env_logger` 是一个常见的选择，但还有像 `fern`、`slog` 或 `tracing` 这样的替代品，每个都有自己的一套功能和配置选项。

实现日志记录时需要考虑的一些事项包括：

1. **日志级别**：控制详细程度是关键。Rust 的 `log` 库定义了几个日志级别：error、warn、info、debug 和 trace，按严重性递减排序。

2. **性能**：日志记录会影响性能。至关重要的是要审慎地使用它，确保避免在性能关键路径中的日志记录或在生产中过度详细的日志。

3. **结构化日志记录**：现代最佳实践涉及结构化日志记录，其中日志以机器可读的格式（如 JSON）编写。像 `slog` 这样的库允许在 Rust 中进行结构化日志记录，可以使用 ELK Stack 或 Splunk 这样的日志管理系统对其进行索引和查询。

4. **异步日志记录**：为了最小化对主应用程序的影响，可以异步进行日志记录。这通常是通过让日志库写入到内存队列中实现的，然后一个单独的线程处理队列并将日志写入目的地。

5. **配置**：许多日志框架支持通过环境变量、配置文件和/或代码进行配置。这种灵活性是在不同环境（开发、暂存、生产）中调整输出的关键。

## 参见

- `log` 库文档：https://docs.rs/log/
- `env_logger` 库文档：https://docs.rs/env_logger/
- Rust by Example 日志页面：https://doc.rust-lang.org/rust-by-example/std_misc/log.html
- `slog` 库，一个备选的日志框架：https://github.com/slog-rs/slog
- Tracing，一个用于检测 Rust 程序的框架：https://crates.io/crates/tracing
