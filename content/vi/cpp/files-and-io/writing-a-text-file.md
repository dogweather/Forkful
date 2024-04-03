---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:12:18.722389-07:00
description: "Vi\u1EBFt m\u1ED9t t\u1EC7p v\u0103n b\u1EA3n trong C++ c\xF3 ngh\u0129\
  a l\xE0 t\u1EA1o ho\u1EB7c ch\u1EC9nh s\u1EEDa m\u1ED9t t\u1EC7p \u0111\u1EC3 l\u01B0\
  u tr\u1EEF d\u1EEF li\u1EC7u v\u0103n b\u1EA3n. L\u1EADp tr\xECnh vi\xEAn th\u1EF1\
  c hi\u1EC7n \u0111\u1EC3 l\u01B0u tr\u1EEF d\u1EEF li\u1EC7u nh\u01B0 c\u1EA5u\u2026"
lastmod: '2024-03-13T22:44:37.066247-06:00'
model: gpt-4-0125-preview
summary: "Vi\u1EBFt m\u1ED9t t\u1EC7p v\u0103n b\u1EA3n trong C++ c\xF3 ngh\u0129\
  a l\xE0 t\u1EA1o ho\u1EB7c ch\u1EC9nh s\u1EEDa m\u1ED9t t\u1EC7p \u0111\u1EC3 l\u01B0\
  u tr\u1EEF d\u1EEF li\u1EC7u v\u0103n b\u1EA3n."
title: "Vi\u1EBFt m\u1ED9t t\u1EC7p v\u0103n b\u1EA3n"
weight: 24
---

## Cách thực hiện:
Dưới đây là một chương trình C++ đơn giản tạo một tệp văn bản và viết "Hello, World!" vào đó.

```c++
#include <fstream>
#include <iostream>

int main() {
    std::ofstream outfile("hello.txt");

    if (outfile.is_open()) {
        outfile << "Hello, World!";
        outfile.close();
        std::cout << "Ghi tệp thành công\n";
    } else {
        std::cout << "Lỗi khi mở tệp\n";
    }

    return 0;
}
```
Kết quả mẫu:
```
Ghi tệp thành công
```

## Đi sâu hơn
Trong C++, tệp được xử lý bởi tiêu đề `<fstream>`, cung cấp `std::ofstream` để ghi, `std::ifstream` để đọc, và `std::fstream` để thực hiện cả hai. Lịch sử, nhập/xuất tệp trong C++ đã phát triển từ cấu trúc `FILE` của C và các hàm liên quan. Các phương án thay thế cho `fstream` bao gồm API đặc thù của nền tảng, thư viện bên thứ ba, hoặc đề xuất C++ hiện đại như cải tiến thư viện hệ thống tệp. Khi ghi tệp, xử lý lỗi và đảm bảo nguồn lực được giải phóng đúng cách, thường sử dụng các mẫu RAII có sẵn trong C++ hiện đại.

## Xem thêm
- Nhập/Xuất tệp C++: http://www.cplusplus.com/doc/tutorial/files/
- Tham khảo C++ (ofstream): https://en.cppreference.com/w/cpp/io/basic_ofstream
- Thư viện Hệ thống Tệp C++: https://en.cppreference.com/w/cpp/filesystem
