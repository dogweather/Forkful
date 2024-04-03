---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:12:54.422720-07:00
description: "Vi\u1EBFt c\xE1c b\xE0i ki\u1EC3m tra gi\xFAp ki\u1EC3m tra xem m\xE3\
  \ c\u1EE7a b\u1EA1n c\xF3 th\u1EF1c hi\u1EC7n \u0111\xFAng nh\u01B0 mong \u0111\u1EE3\
  i hay kh\xF4ng, b\u1EAFt \u0111\u01B0\u1EE3c l\u1ED7i s\u1EDBm. C\xE1c l\u1EADp\
  \ tr\xECnh vi\xEAn th\u1EF1c hi\u1EC7n ki\u1EC3m tra \u0111\u1EC3\u2026"
lastmod: '2024-03-13T22:44:37.047256-06:00'
model: gpt-4-0125-preview
summary: "Vi\u1EBFt c\xE1c b\xE0i ki\u1EC3m tra gi\xFAp ki\u1EC3m tra xem m\xE3 c\u1EE7\
  a b\u1EA1n c\xF3 th\u1EF1c hi\u1EC7n \u0111\xFAng nh\u01B0 mong \u0111\u1EE3i hay\
  \ kh\xF4ng, b\u1EAFt \u0111\u01B0\u1EE3c l\u1ED7i s\u1EDBm."
title: "Vi\u1EBFt c\xE1c b\xE0i ki\u1EC3m tra"
weight: 36
---

## Làm thế nào:
Hãy sử dụng một hàm C++ đơn giản và một bài kiểm tra sử dụng framework Catch2.

```cpp
// main.cpp
#define CATCH_CONFIG_MAIN  // Cho phép Catch cung cấp main().
#include <catch2/catch.hpp>

int Add(int a, int b) {
    return a + b;
}

TEST_CASE( "Phép cộng hoạt động", "[toán]" ) {
    REQUIRE( Add(2, 2) == 4 );
}
```
Biên dịch với `g++ -std=c++17 main.cpp -o test -lcatch2` và chạy `./test`. Đầu ra mẫu:

```
Tất cả các bài kiểm tra đã vượt qua (1 tuyên bố trong 1 trường hợp kiểm tra)
```

## Sâu hơn
Việc kiểm tra không phải lúc nào cũng là quy chuẩn. Trong những năm '70, nó được thực hiện bằng tay. Giờ đây, các bài kiểm tra tự động là chìa khóa trong phương pháp agile và TDD (Phát triển dựa trên kiểm tra). Các lựa chọn thay thế cho Catch2? Google Test, Boost.Test, và CppUnit, mỗi cái có những đặc điểm riêng biệt. Nhớ rằng: các bài kiểm tra đánh giá xem mã có đáp ứng được yêu cầu hay không, không phải là yêu cầu đó có chính xác hay không—đó là vấn đề của spec.

## Xem thêm
- Catch2: https://github.com/catchorg/Catch2
- Google Test: https://github.com/google/googletest
- Boost.Test: https://www.boost.org/doc/libs/release/libs/test/
- CppUnit: https://freedesktop.org/wiki/Software/cppunit/
