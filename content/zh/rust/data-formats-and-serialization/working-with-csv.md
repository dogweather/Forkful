---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:28.017722-07:00
description: "\u5904\u7406 CSV\uFF08\u9017\u53F7\u5206\u9694\u503C\uFF09\u6587\u4EF6\
  \u6D89\u53CA\u8BFB\u53D6\u548C\u5199\u5165\u5B58\u50A8\u8868\u683C\u6570\u636E\u7684\
  \u7EAF\u6587\u672C\u6587\u4EF6\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\u4E3A\
  \u4E86\u5B9E\u73B0\u4E0D\u540C\u7A0B\u5E8F\u3001\u7CFB\u7EDF\u4E4B\u95F4\u7684\u6570\
  \u636E\u5171\u4EAB\uFF0C\u6216\u8005\u9AD8\u6548\u3001\u53EF\u8BFB\u5730\u5904\u7406\
  \u5927\u578B\u6570\u636E\u96C6\u3002"
lastmod: '2024-03-13T22:44:47.547132-06:00'
model: gpt-4-0125-preview
summary: "\u5904\u7406 CSV\uFF08\u9017\u53F7\u5206\u9694\u503C\uFF09\u6587\u4EF6\u6D89\
  \u53CA\u8BFB\u53D6\u548C\u5199\u5165\u5B58\u50A8\u8868\u683C\u6570\u636E\u7684\u7EAF\
  \u6587\u672C\u6587\u4EF6\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\u4E3A\u4E86\
  \u5B9E\u73B0\u4E0D\u540C\u7A0B\u5E8F\u3001\u7CFB\u7EDF\u4E4B\u95F4\u7684\u6570\u636E\
  \u5171\u4EAB\uFF0C\u6216\u8005\u9AD8\u6548\u3001\u53EF\u8BFB\u5730\u5904\u7406\u5927\
  \u578B\u6570\u636E\u96C6\u3002."
title: "\u5904\u7406CSV\u6587\u4EF6"
weight: 37
---

## 如何操作：
Rust 以其对安全性和性能的重视，提供了出色的 crates（库）来处理 CSV 文件，其中 `csv` 是最受欢迎的。你还需要 `serde` 来序列化和反序列化数据。

首先，将依赖项添加到你的 `Cargo.toml`：

```toml
[dependencies]
csv = "1.1"
serde = { version = "1.0", features = ["derive"] }
```

### 读取 CSV
要读取 CSV 文件，定义一个表示你数据的结构体并从 `serde` 导出 `Deserialize`：

```rust
use serde::Deserialize;
use std::error::Error;
use std::fs::File;
use std::io;
use std::process;

#[derive(Debug, Deserialize)]
struct Record {
    city: String,
    state: String,
    population: u64,
}

fn read_from_csv(file_path: &str) -> Result<(), Box<dyn Error>> {
    let file = File::open(file_path)?;
    let mut rdr = csv::Reader::from_reader(file);

    for result in rdr.deserialize() {
        let record: Record = result?;
        println!("{:?}", record);
    }
    Ok(())
}

fn main() {
    if let Err(err) = read_from_csv("cities.csv") {
        println!("error running example: {}", err);
        process::exit(1);
    }
}
```

对于包含城市信息的 CSV，示例输出可能看起来像：
```plaintext
Record { city: "西雅图", state: "WA", population: 744955 }
Record { city: "纽约", state: "NY", population: 8336817 }
```

### 写入 CSV
要写入 CSV 文件，定义一个结构体并从 `Serialize` 导出：

```rust
use serde::Serialize;
use std::error::Error;
use std::fs::File;

#[derive(Serialize)]
struct Record {
    city: String,
    state: String,
    population: u64,
}

fn write_to_csv(file_path: &str, records: Vec<Record>) -> Result<(), Box<dyn Error>> {
    let file = File::create(file_path)?;
    let mut wtr = csv::Writer::from_writer(file);

    for record in records {
        wtr.serialize(&record)?;
    }
    wtr.flush()?;
    Ok(())
}

fn main() -> Result<(), Box<dyn Error>> {
    let records = vec![
        Record {
            city: "洛杉矶".into(),
            state: "CA".into(),
            population: 3979563,
        },
        Record {
            city: "芝加哥".into(),
            state: "IL".into(),
            population: 2695598,
        },
    ];

    write_to_csv("output.csv", records)?;

    Ok(())
}
```

这将创建包含数据的 `output.csv`：

```csv
city,state,population
洛杉矶,CA,3979563
芝加哥,IL,2695598
```

通过利用 Rust 强大的类型系统和健壮的生态系统 crates，处理 CSV 数据变得既高效又简单，确保了你的数据处理任务的安全性和性能。
