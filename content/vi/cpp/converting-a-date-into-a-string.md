---
title:                "Chuyển đổi một ngày thành chuỗi"
aliases:
- vi/cpp/converting-a-date-into-a-string.md
date:                  2024-01-28T21:57:47.944017-07:00
model:                 gpt-4-0125-preview
simple_title:         "Chuyển đổi một ngày thành chuỗi"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/cpp/converting-a-date-into-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Lý do và Mục đích:
Chuyển đổi một ngày thành chuỗi trong C++ biến đối tượng ngày thành định dạng văn bản dễ đọc. Điều này rất quan trọng để hiển thị ngày cho người dùng và ghi nhận các sự kiện một cách thân thiện với người dùng.

## Cách thực hiện:
Trong C++ hiện đại, thư viện `<chrono>` và `<iomanip>` là người bạn đồng hành của bạn cho các thao tác ngày-giờ. Dưới đây là một phương pháp nhanh chóng sử dụng `std::put_time`:

```cpp
#include <iostream>
#include <iomanip>
#include <chrono>
#include <sstream>

int main() {
    auto now = std::chrono::system_clock::now(); // Lấy thời gian hiện tại
    auto time = std::chrono::system_clock::to_time_t(now); // Chuyển đổi thành time_t
    
    // Chuyển đổi thành cấu trúc tm để định dạng
    std::tm tm = *std::localtime(&time);

    // Luồng chuỗi cho đầu ra
    std::stringstream ss;

    ss << std::put_time(&tm, "%Y-%m-%d %H:%M:%S"); // Định dạng: YYYY-MM-DD HH:MM:SS

    std::string date_str = ss.str(); // Chuyển đổi thành chuỗi

    std::cout << date_str << std::endl; // Xuất chuỗi ngày
    return 0;
}
```

Ví dụ về đầu ra (tùy thuộc vào ngày và giờ hiện tại):
```
2023-03-15 14:25:30
```

## Tìm hiểu kỹ lưỡng
Trước khi `<chrono>` được giới thiệu, các lập trình viên C++ thường phải vật lộn với việc xử lý thời gian theo phong cách C qua `<ctime>`. Điều này kém trực quan và dễ mắc lỗi hơn do quản lý bộ nhớ thủ công và những đặc thù phụ thuộc vào nền tảng.

Các phương án thay thế cho `std::put_time` bao gồm việc sử dụng `strftime`, nhưng đó là cách làm mang phong cách C. Các thư viện bên thứ ba như Boost.Date_Time có thể cung cấp nhiều chức năng hơn nhưng có chi phí thêm phụ thuộc.

Một chi tiết thực hiện quan trọng là hiểu các chỉ định định dạng trong `std::put_time`, giống với những gì được sử dụng trong `strftime`. Bạn đang ánh xạ các trình giữ chỗ cho các thành phần ngày hoặc giờ — `%Y` cho năm đầy đủ, `%m` cho tháng, v.v.

## Xem thêm
- [Tài liệu `<chrono>`](https://en.cppreference.com/w/cpp/header/chrono)
- [Tài liệu `<iomanip>`](https://en.cppreference.com/w/cpp/header/iomanip)
- [Boost.Date_Time](https://www.boost.org/doc/libs/release/libs/date_time/)
