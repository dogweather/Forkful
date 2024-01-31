---
title:                "Lấy ngày hiện tại"
date:                  2024-01-28T22:01:45.011623-07:00
model:                 gpt-4-0125-preview
simple_title:         "Lấy ngày hiện tại"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/rust/getting-the-current-date.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## **Cái gì & Tại sao?**

Trong lập trình, việc lấy ngày tháng hiện tại giúp theo dõi sự kiện hoặc ghi lại dữ liệu. Nó rất hữu ích cho việc đánh dấu thời gian, lập lịch, hoặc chỉ đơn giản là biết khi nào một điều gì đó xảy ra.

## **Cách thực hiện:**

```Rust
use chrono::{DateTime, Local};

fn main() {
    let now: DateTime<Local> = Local::now();
    println!("{}", now.format("%Y-%m-%d %H:%M:%S"));
}
```

Đầu ra:
```
2023-04-05 14:20:35
```

## **Tìm hiểu sâu hơn**

Rust, một ngôn ngữ hệ thống tập trung vào an toàn và hiệu suất, không được trang bị các chức năng ngày và giờ trong thư viện chuẩn của mình. Thay vào đó, cộng đồng xây dựng các crate—thuật ngữ của Rust cho thư viện hoặc gói. Một điển hình là `chrono`.

`chrono` cung cấp các tính năng datetime phong phú. Hơn nữa, nó xử lý các múi giờ, không phải là điều đơn giản. Crate sử dụng dữ liệu múi giờ từ `IANA` (Cơ Quan Phân Số Internet) để chính xác biểu diễn ngày và giờ địa phương.

Các crate khác như `time` tồn tại nhưng có thể có giao diện hoặc tính năng khác nhau. Đối với nhu cầu nhẹ hơn, `time` có thể nhanh hơn và có ít phụ thuộc hơn.

Lấy thời gian địa phương liên quan đến việc gọi hệ thống tương tác với hệ điều hành. Độ chính xác và độ chặt chẽ có thể thay đổi và bị ảnh hưởng bởi hệ thống và cấu hình của nó.

Các chi tiết thực thi cũng đáng được nhìn nhận dưới góc độ triết lý thiết kế. Rust ưa chuộng sự rõ ràng. Vì vậy, khi bạn lấy thời gian hiện tại, bạn chọn rõ ràng giữa thời gian địa phương so với UTC, ý thức về múi giờ, v.v.—giảm thiểu bất ngờ và thúc đẩy sự có chủ ý trong mã.

## **Xem thêm:**

- Tài liệu crate `chrono` của Rust: https://docs.rs/chrono/
- Tài liệu crate `time` của Rust: https://docs.rs/time/
- Cơ sở dữ liệu múi giờ của `IANA`: https://www.iana.org/time-zones
