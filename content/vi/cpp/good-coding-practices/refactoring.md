---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:06:50.324749-07:00
description: "T\xE1i c\u1EA5u tr\xFAc l\xE0 qu\xE1 tr\xECnh thay \u0111\u1ED5i c\u1EA5\
  u tr\xFAc n\u1ED9i b\u1ED9 c\u1EE7a m\u1ED9t ch\u01B0\u01A1ng tr\xECnh m\xE1y t\xED\
  nh m\xE0 kh\xF4ng l\xE0m thay \u0111\u1ED5i h\xE0nh vi b\xEAn ngo\xE0i c\u1EE7a\
  \ n\xF3. L\u1EADp tr\xECnh vi\xEAn th\u1EF1c hi\u1EC7n\u2026"
lastmod: '2024-03-13T22:44:37.053606-06:00'
model: gpt-4-0125-preview
summary: "T\xE1i c\u1EA5u tr\xFAc l\xE0 qu\xE1 tr\xECnh thay \u0111\u1ED5i c\u1EA5\
  u tr\xFAc n\u1ED9i b\u1ED9 c\u1EE7a m\u1ED9t ch\u01B0\u01A1ng tr\xECnh m\xE1y t\xED\
  nh m\xE0 kh\xF4ng l\xE0m thay \u0111\u1ED5i h\xE0nh vi b\xEAn ngo\xE0i c\u1EE7a\
  \ n\xF3."
title: "T\xE1i c\u1EA5u tr\xFAc m\xE3"
weight: 19
---

## Làm thế nào:
Hãy tưởng tượng bạn có một hàm đang làm quá nhiều thứ, như phương thức cồng kềnh này vừa khởi tạo một đối tượng và cũng thực hiện ghi log:

```C++
#include <iostream>

class Widget {
public:
    void init(bool verbose) {
        // Logic khởi tạo
        // ...

        // Ghi log mức độ chi tiết
        if (verbose) {
            std::cout << "Widget initialized!" << std::endl;
        }
    }
};

// Cách sử dụng:
Widget w;
w.init(true);
```

Đầu ra:
```
Widget initialized!
```

Việc tái cấu trúc này thành các phương thức rõ ràng, dễ hiểu hơn có thể như sau:

```C++
#include <iostream>

class Widget {
public:
    void init() {
        // Chỉ logic khởi tạo
        // ...
    }

    void logInitialization() const {
        std::cout << "Widget initialized!" << std::endl;
    }
};

// Cách sử dụng:
Widget w;
w.init();
w.logInitialization();
```

Thay đổi này không làm thay đổi hành vi của chương trình nhưng làm cho lớp `Widget` trở nên linh hoạt hơn và cách sử dụng rõ ràng hơn.

## Sâu hơn nữa
Khái niệm tái cấu trúc như chúng ta biết ngày nay có nguồn gốc từ cộng đồng lập trình Smalltalk của những năm 1980 và được phổ biến rộng rãi bởi cuốn sách "Refactoring: Improving the Design of Existing Code" của Martin Fowler phát hành năm 1999. Ngày nay, tái cấu trúc là một phần cốt lõi của phát triển phần mềm hiện đại, được tích hợp vào các phương pháp phát triển khác nhau như Agile và TDD (Phát triển Dựa trên Kiểm thử).

Khi chúng ta nói về các phương án thay thế cho việc tái cấu trúc, chúng ta bước vào lãnh địa của viết mới hoặc thiết kế lại. Tái cấu trúc là chiến lược và tăng cường, trong khi viết mới có thể loại bỏ mã hiện có để ưu tiên một giải pháp mới. Trong khi đó, thiết kế lại có thể đòi hỏi những thay đổi đáng kể hơn bao gồm thay đổi chức năng, là một mục tiêu không phải của việc tái cấu trúc murn.

Các chi tiết thực thi về tái cấu trúc có thể trở nên rất chi tiết. Có nhiều 'mùi mã' có thể thúc đẩy một sự tái cấu trúc, như phương thức dài, lớp lớn, hoặc mã trùng lặp. Có các công cụ tự động tồn tại có thể hỗ trợ trong việc tái cấu trúc, như "Clang-Tidy" cho C++, có thể nhận biết vấn đề và thậm chí áp dụng một số sửa chữa.

Hơn nữa, việc tái cấu trúc đòi hỏi một bộ kiểm thử vững chắc để đảm bảo chức năng không bị thay đổi. Không có kiểm thử, bạn cơ bản đang mù quáng và đối mặt với nguy cơ lỗi.

## Xem thêm
Để hiểu sâu hơn về tái cấu trúc và xem thêm ví dụ, bạn có thể muốn xem:

- Text cổ điển của Martin Fowler "Refactoring: Improving the Design of Existing Code" cho những ý tưởng và chiến lược cơ bản.
- Tài liệu `Clang-Tidy` tại https://clang.llvm.org/extra/clang-tidy/ cho hỗ trợ tái cấu trúc tự động trong C++.
- "Working Effectively with Legacy Code" của Michael Feathers, cung cấp các kỹ thuật để tái cấu trúc an toàn trong bối cảnh mã nguồn hiện hữu không hoàn hảo.
