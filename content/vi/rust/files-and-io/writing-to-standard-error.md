---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:13:55.286144-07:00
description: "Vi\u1EBFt v\xE0o l\u1ED7i chu\u1EA9n (stderr) l\xE0 \u0111\u01B0a ra\
  \ v\u0103n b\u1EA3n v\xE0o d\xF2ng l\u1ED7i, ri\xEAng bi\u1EC7t v\u1EDBi \u0111\u1EA7\
  u ra chu\u1EA9n (stdout). L\u1EADp tr\xECnh vi\xEAn l\xE0m \u0111i\u1EC1u n\xE0\
  y \u0111\u1EC3 ghi nh\u1EADn l\u1ED7i v\xE0 th\xF4ng\u2026"
lastmod: '2024-03-13T22:44:36.397998-06:00'
model: gpt-4-0125-preview
summary: "Vi\u1EBFt v\xE0o l\u1ED7i chu\u1EA9n (stderr) l\xE0 \u0111\u01B0a ra v\u0103\
  n b\u1EA3n v\xE0o d\xF2ng l\u1ED7i, ri\xEAng bi\u1EC7t v\u1EDBi \u0111\u1EA7u ra\
  \ chu\u1EA9n (stdout)."
title: "Ghi v\xE0o l\u1ED7i chu\u1EA9n"
weight: 25
---

## Làm thế nào:
Rust làm cho việc viết vào stderr trở nên đơn giản. Sử dụng macro `eprintln!` cho văn bản, giống như `println!` nhưng dành cho lỗi.

```Rust
fn main() {
    // Đầu ra thường thức
    println!("Đây là một thông điệp bình thường.");

    // Đầu ra lỗi
    eprintln!("Đây là một thông điệp lỗi.");
}
```

Đầu ra mẫu:

```shell
Đây là một thông điệp bình thường.
Đây là một thông điệp lỗi.
```

Chú ý rằng thông điệp lỗi chuyển đi stderr. Trên một cửa sổ dòng lệnh, bạn sẽ không thấy sự khác biệt. Tuy nhiên, nếu bạn chuyển hướng stdout, stderr vẫn hiện lên trong cửa sổ dòng lệnh.

```shell
$ cargo run > output.txt
Đây là một thông điệp lỗi.
```

Ở đây `output.txt` chỉ chứa "Đây là một thông điệp bình thường."

## Sâu hơn
Theo lịch sử, việc tách biệt stdout và stderr cho phép các hệ thống Unix xử lý dữ liệu thường thức và lỗi một cách khác nhau. Đây là một phương pháp tốt và giúp ích cho việc tự động hóa và ghi nhật ký.

Các lựa chọn thay thế cho việc viết vào stderr ở mức thấp hơn, như sử dụng `std::io::stderr`. Nó cung cấp nhiều quyền kiểm soát hơn và làm việc tốt với dữ liệu không phải văn bản.

```Rust
use std::io::{self, Write};

fn main() -> io::Result<()> {
    let stderr = &mut std::io::stderr();
    
    // Viết trực tiếp một chuỗi vào stderr
    writeln!(stderr, "Lỗi: Không thể hoàn thành thao tác")?;
    
    Ok(())
}
```

Bên dưới lớp vỏ, `eprintln!` là một macro đóng gói `writeln!` vào stderr, giữ cho mọi thứ được DRY (Don’t Repeat Yourself - Đừng Lặp Lại Chính Mình).

## Xem Thêm
Để biết thêm về xử lý lỗi và ghi nhật ký:

- Rust By Example về stdio: https://doc.rust-lang.org/rust-by-example/std_misc/stdio.html
- Sách Rust về Xử lý Lỗi: https://doc.rust-lang.org/book/ch09-00-error-handling.html
- Công cụ `log` của Rust để thiết lập ghi nhật ký toàn diện hơn: https://crates.io/crates/log
