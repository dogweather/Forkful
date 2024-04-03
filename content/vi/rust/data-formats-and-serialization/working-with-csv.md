---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:20.089059-07:00
description: "CSV, vi\u1EBFt t\u1EAFt c\u1EE7a Comma-Separated Values (Gi\xE1 tr\u1ECB\
  \ \u0110\u01B0\u1EE3c Ph\xE2n C\xE1ch B\u1EB1ng D\u1EA5u Ph\u1EA9y), l\xE0 m\u1ED9\
  t \u0111\u1ECBnh d\u1EA1ng t\u1EC7p \u0111\u01B0\u1EE3c s\u1EED d\u1EE5ng \u0111\
  \u1EC3 l\u01B0u tr\u1EEF d\u1EEF li\u1EC7u d\u1EA1ng b\u1EA3ng. C\xE1c l\u1EADp\u2026"
lastmod: '2024-03-13T22:44:36.405854-06:00'
model: gpt-4-0125-preview
summary: "CSV, vi\u1EBFt t\u1EAFt c\u1EE7a Comma-Separated Values (Gi\xE1 tr\u1ECB\
  \ \u0110\u01B0\u1EE3c Ph\xE2n C\xE1ch B\u1EB1ng D\u1EA5u Ph\u1EA9y), l\xE0 m\u1ED9\
  t \u0111\u1ECBnh d\u1EA1ng t\u1EC7p \u0111\u01B0\u1EE3c s\u1EED d\u1EE5ng \u0111\
  \u1EC3 l\u01B0u tr\u1EEF d\u1EEF li\u1EC7u d\u1EA1ng b\u1EA3ng."
title: "L\xE0m vi\u1EC7c v\u1EDBi CSV"
weight: 37
---

## Cách thực hiện:
Đầu tiên, bao gồm crate cần thiết trong `Cargo.toml`:

```toml
[dependencies]
csv = "1.1"
```

Sau đó, xử lý đọc một CSV:

```rust
use csv::Reader;
use std::error::Error;

fn main() -> Result<(), Box<dyn Error>> {
    let mut rdr = Reader::from_path("data.csv")?;
    for result in rdr.records() {
        let record = result?;
        println!("{:?}", record);
    }
    Ok(())
}
```

Viết vào một CSV:

```rust
use csv::Writer;
use std::error::Error;

fn main() -> Result<(), Box<dyn Error>> {
    let mut wtr = Writer::from_path("output.csv")?;
    wtr.write_record(&["name", "city", "age"])?;
    wtr.write_record(&["Jane", "New York", "30"])?;
    wtr.flush()?;
    Ok(())
}
```

Kết quả mẫu khi đọc:

```
StringRecord(["Jane", "New York", "30"])
```

## Sâu hơn
CSV đã tồn tại từ những ngày đầu của máy tính cá nhân, được sử dụng cho việc trao đổi dữ liệu giữa các chương trình và hệ thống. Mặc dù JSON và XML cung cấp nhiều cấu trúc hơn, CSV vẫn được ưa chuộng vì tính nhẹ và dễ sử dụng của nó.

Các lựa chọn thay thế cho crate csv trong Rust bao gồm `serde_csv`, cung cấp serialisation và deserialization thuận tiện, và `papercut`, tập trung vào việc phân tích cú pháp CSV an toàn và thuận tiện.

Phân tích cú pháp CSV trong Rust bị giới hạn bởi I/O. Việc xử lý hiệu quả liên quan đến việc sử dụng iterators và xử lý lỗi mạnh mẽ của Rust để quản lý dữ liệu bị lỗi.

## Xem Thêm
- Tài liệu về crate CSV của Rust: https://docs.rs/csv/
- Sách về Ngôn ngữ Lập trình Rust: https://doc.rust-lang.org/book/
- Serde: https://serde.rs/ - một framework cho việc serializing và deserializing các cấu trúc dữ liệu của Rust.
- Rust by Example CSV: https://rustbyexample.com/std_misc/file/csv.html
