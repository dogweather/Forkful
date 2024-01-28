---
title:                "从字符串中移除引号"
date:                  2024-01-26T03:41:44.171026-07:00
model:                 gpt-4-0125-preview
simple_title:         "从字符串中移除引号"
programming_language: "Rust"
category:             "Rust"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/rust/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## 什么与为什么？

在 Rust 中删除字符串中的引号是关于去除可能包裹在文本数据周围的不必要的额外引号字符。程序员在需要清理或规范化字符串时会这样做，可能是在从文件解析数据之后，或是在为另一种可能会因引号而出现问题或冗余的格式准备数据时。

## 如何操作：

```Rust
fn remove_quotes(s: &str) -> String {
    s.trim_matches(|c| c == '\"' || c == '\'').to_string()
}

fn main() {
    let quoted_str = "\"你好，Rustaceans!\"";
    let cleaned_str = remove_quotes(quoted_str);
    println!("{}", cleaned_str);
    // 输出：你好，Rustaceans!
}
```

有时你可能会碰到一个含有混合引号的字符串，像这样：

```Rust
fn main() {
    let mixed_quoted = "'Rust说：\"你好，世界!\"'";
    let cleaned_str = remove_quotes(mixed_quoted);
    println!("{}", cleaned_str);
    // 输出：Rust说："你好，世界!"
}
```

在这里，只有最外层的单引号被移除了。

## 深入解析

当从字符串中移除引号时，你可能会想知道为什么不只是简单地使用 `.replace("\"", "")`。早期，处理文本的标准化较少，不同系统有存储和传输文本的不同方式，通常对特殊字符使用某种“转义序列”。Rust 的 `trim_matches` 方法更加多功能，允许你指定多个要修剪的字符，以及是从字符串的开始（前缀）、结束（后缀）还是两侧进行修剪。

当然也有替代方法。Regex 是字符串操作的强大工具，能够匹配复杂的模式，而且对于仅仅移除引号来说可能有点大材小用。像 `trim_in_place` 这样的库能提供原地修剪而不需要创建新的 `String` 对象，这对于性能关键的应用来说可能是可取的。

在底层，`trim_matches` 实际上是从字符串的两端开始，通过字符地迭代检查所提供的模式，直到找到不匹配的字符。对于它所做的工作而言，它是高效的，但总是要意识到它是在处理 Unicode 标量值。如果你的字符串可能包含多字节的 Unicode 字符，你不必担心它会将它们分开。

## 参见

- Rust 关于字符串操作的文档：https://doc.rust-lang.org/book/ch08-02-strings.html
- 用于复杂模式的 `regex` 库：https://crates.io/crates/regex
- Rust 通过实例学习编程场景：https://doc.rust-lang.org/stable/rust-by-example/std/str.html
