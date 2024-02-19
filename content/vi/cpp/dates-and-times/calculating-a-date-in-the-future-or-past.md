---
aliases:
- /vi/cpp/calculating-a-date-in-the-future-or-past/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:55:53.266021-07:00
description: "T\xEDnh to\xE1n m\u1ED9t ng\xE0y trong t\u01B0\u01A1ng lai ho\u1EB7\
  c qu\xE1 kh\u1EE9 c\xF3 ngh\u0129a l\xE0 x\xE1c \u0111\u1ECBnh ng\xE0y n\xE0o \u0111\
  \xF3 s\u1EBD l\xE0 sau ho\u1EB7c tr\u01B0\u1EDBc m\u1ED9t kho\u1EA3ng th\u1EDDi\
  \ gian nh\u1EA5t \u0111\u1ECBnh. N\xF3 h\u1EEFu \xEDch cho vi\u1EC7c\u2026"
lastmod: 2024-02-18 23:08:51.059003
model: gpt-4-0125-preview
summary: "T\xEDnh to\xE1n m\u1ED9t ng\xE0y trong t\u01B0\u01A1ng lai ho\u1EB7c qu\xE1\
  \ kh\u1EE9 c\xF3 ngh\u0129a l\xE0 x\xE1c \u0111\u1ECBnh ng\xE0y n\xE0o \u0111\xF3\
  \ s\u1EBD l\xE0 sau ho\u1EB7c tr\u01B0\u1EDBc m\u1ED9t kho\u1EA3ng th\u1EDDi gian\
  \ nh\u1EA5t \u0111\u1ECBnh. N\xF3 h\u1EEFu \xEDch cho vi\u1EC7c\u2026"
title: "T\xEDnh to\xE1n ng\xE0y trong t\u01B0\u01A1ng lai ho\u1EB7c qu\xE1 kh\u1EE9"
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Tính toán một ngày trong tương lai hoặc quá khứ có nghĩa là xác định ngày nào đó sẽ là sau hoặc trước một khoảng thời gian nhất định. Nó hữu ích cho việc tạo nhắc nhở, thiết lập ngày hết hạn, lên lịch sự kiện, hoặc đơn giản là ghi chép xem đã qua bao nhiêu thời gian.

## Làm sao:
C++20 đã giới thiệu các nâng cấp thư viện `<chrono>`, vì vậy xử lý thời gian ít phức tạp hơn. Dưới đây là một ví dụ nhanh về việc thêm ngày vào ngày hiện tại:

```C++
#include <iostream>
#include <chrono>
#include <format>

using namespace std::chrono;

int main() {
    // Lấy ngày hôm nay
    auto today = floor<days>(system_clock::now());
    
    // Thêm 30 ngày vào hôm nay
    auto future_date = today + days(30);
    
    // Chuyển đổi thành time_point để xuất ra sử dụng system_clock
    auto tp = system_clock::time_point(future_date);
    
    // Xuất ra
    std::cout << "Ngày hôm nay: "
              << std::format("{:%F}\n", today);
    std::cout << "Ngày tương lai (30 ngày sau): "
              << std::format("{:%F}\n", tp);
    return 0;
}
```

Kết quả mẫu:
```
Ngày hôm nay: 2023-03-15
Ngày tương lai (30 ngày sau): 2023-04-14
```

Cách trừ ngày hoạt động tương tự - bạn chỉ sử dụng `-` thay vì `+`.

## Đào sâu
Trước C++20, bạn có thể sẽ sử dụng một thư viện như Boost để thao tác với ngày. Nhưng `<chrono>` được cập nhật đơn giản hóa nó với các kiểu `system_clock`, `year_month_day`, và `duration`.

Trong lịch sử, việc tính toán ngày tháng là phức tạp do việc xử lý thủ công chiều dài tháng biến đổi, năm nhuận, và múi giờ. `<chrono>` của C++20 giải quyết những vấn đề này bằng cách cung cấp hỗ trợ lịch và múi giờ.

Có phương án thay thế không? Bạn vẫn có thể sử dụng Boost hoặc thậm chí tự mình tạo logic ngày tháng (phiêu lưu, nhưng tại sao lại thế?). Cũng có các thư viện bên thứ ba như thư viện "ngày" của Howard Hinnant, đóng một vai trò quan trọng trong các cập nhật chrono của C++20.

Về mặt triển khai, `<chrono>` xác định thời lượng là các hằng số hợp lý tại thời điểm biên dịch, tránh vấn đề về số dấu phẩy động. Các kiểu như `year_month_day` dựa trên `sys_days`, đại diện cho một time_point là số ngày kể từ một kỷ nguyên chung (1970-01-01).

## Xem thêm
- Tham khảo C++ cho `chrono`: https://en.cppreference.com/w/cpp/header/chrono
- Thư viện Ngày của Howard Hinnant (tiền thân cho các cập nhật chrono của C++20): https://github.com/HowardHinnant/date
- Tài liệu về Date/Time của Boost: https://www.boost.org/doc/libs/release/libs/date_time/
