---
title:                "处理XML"
aliases:
- /zh/rust/working-with-xml/
date:                  2024-01-26T04:36:09.565903-07:00
model:                 gpt-4-0125-preview
simple_title:         "处理XML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/rust/working-with-xml.md"
---

{{< edit_this_page >}}

## 什么 & 为什么？
XML，即可扩展标记语言（eXtensible Markup Language），就像是JSON那个冗长的堂兄。当处理遗留系统、企业软件或未跟随JSON潮流的API时，你将不得不与XML打交道。在需要数据交换的地方，XML依然稳固地站着。

## 如何操作：
在Rust中，你可以使用像`xml-rs`这样的crate来处理XML。通过将`xml-rs = "0.8"`添加到你的`Cargo.toml`来安装。下面是解析一个简单XML的方法：

```rust
extern crate xml;

use xml::reader::{EventReader, XmlEvent};

fn main() {
    let xml_data = r#"<book category="fiction">
    <title>Rust in Action</title>
    <author>Tim McNamara</author>
    <year>2021</year>
</book>"#;

    let parser = EventReader::from_str(xml_data);
    for e in parser {
        match e {
            Ok(XmlEvent::StartElement { name, .. }) => {
                println!("开始: {}", name);
            }
            Ok(XmlEvent::Characters(data)) => {
                println!("文本: {}", data);
            }
            Ok(XmlEvent::EndElement { name }) => {
                println!("结束: {}", name);
            }
            Err(e) => {
                println!("错误: {}", e);
            }
            _ => {}
        }
    }
}
```

输出：
```
开始: book
开始: title
文本: Rust in Action
结束: title
开始: author
文本: Tim McNamara
结束: author
开始: year
文本: 2021
结束: year
结束: book
```
这段代码通过流式读取XML，处理开始和结束元素以及文本数据，记录每一步。

## 深入探讨：
XML在技术领域算是资历较深的，它是在90年代末为网络设计的。它的设计强调可读性（对机器和人类都是）以及广泛的自我描述数据。

有替代方案吗？当然，JSON是现代网络API的首选，更轻量且噪音更少。与此同时，YAML因其清晰的布局而赢得了配置文件的青睐。但XML不会很快消失——大量基础设施是建立在它的基础上的。

Rust处理XML的底层借助了迭代器模式，保持低内存使用和高性能。你会发现像`serde-xml-rs`这样的crate提供了类似serde的体验——这对于那些习惯处理JSON的人来说是个好消息。

## 另请参阅：
有关Rust和XML的更多信息：
- `serde-xml-rs` 适用于Rust的serde兼容性：[https://github.com/RReverser/serde-xml-rs](https://github.com/RReverser/serde-xml-rs)
- 官方Rust文档（因为复习永远不是坏事）：[https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/)
