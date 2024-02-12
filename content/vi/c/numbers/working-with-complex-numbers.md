---
title:                "Làm việc với số phức"
aliases:
- /vi/c/working-with-complex-numbers/
date:                  2024-02-03T18:14:09.033437-07:00
model:                 gpt-4-0125-preview
simple_title:         "Làm việc với số phức"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/c/working-with-complex-numbers.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Số phức bao gồm một phần thực và một phần ảo, được biểu diễn dưới dạng `a + bi` trong đó `i` là căn bậc hai của `-1`. Các lập trình viên làm việc với số phức trong nhiều lĩnh vực như kỹ thuật điện, tính toán lượng tử và động lực học chất lỏng, tận dụng các đặc tính độc đáo của chúng cho mô phỏng, xử lý tín hiệu, và giải các loại phương trình toán học cụ thể.

## Làm thế nào:

Trong C, số phức được hỗ trợ bởi Thư viện Tiêu chuẩn, cụ thể là `<complex.h>`. Để sử dụng chúng, khai báo các biến với kiểu `double complex` (hoặc `float complex` cho độ chính xác đơn). Dưới đây là cách thực hiện các phép toán cơ bản:

```c
#include <stdio.h>
#include <complex.h>

int main() {
    double complex z1 = 1.0 + 2.0*I; // Khai báo một số phức 1+2i
    double complex z2 = 1.0 - 2.0*I; // Khai báo một số phức khác 1-2i
    
    // Cộng
    double complex sum = z1 + z2;
    printf("Tổng: %.2f + %.2fi\n", creal(sum), cimag(sum)); // Đầu ra: Tổng: 2.00 + 0.00i

    // Nhân
    double complex product = z1 * z2;
    printf("Tích: %.2f + %.2fi\n", creal(product), cimag(product)); // Đầu ra: Tích: 5.00 + 0.00i

    // Liên hợp
    double complex conjugate = conj(z1);
    printf("Liên hợp của z1: %.2f + %.2fi\n", creal(conjugate), cimag(conjugate)); // Đầu ra: Liên hợp của z1: 1.00 - 2.00i
    
    // Độ lớn
    double magnitude = cabs(z1);
    printf("Độ lớn của z1: %.2f\n", magnitude); // Đầu ra: Độ lớn của z1: 2.24

    // Pha
    double phase = carg(z1);
    printf("Pha của z1: %.2f\n", phase); // Đầu ra bằng radian
    
    return 0;
}
```
Lưu ý rằng `I` là một hằng số biểu thị đơn vị ảo trong `<complex.h>`. Các hàm như `creal()` và `cimag()` được sử dụng để trích xuất phần thực và phần ảo tương ứng, trong khi `conj()` tính toán liên hợp phức. Đối với độ lớn và pha (arg) của số phức, `cabs()` và `carg()` được sử dụng.

## Sâu hơn

Việc hỗ trợ số phức trong C tương đối mới, được chuẩn hóa trong C99. Trước đó, việc tính toán số phức trong C khá cồng kềnh, thường yêu cầu cấu trúc dữ liệu và hàm tùy chỉnh. Sự bao gồm của `<complex.h>` và các loại dữ liệu phức đã tăng cường đáng kể khả năng của ngôn ngữ cho các ứng dụng khoa học và kỹ thuật. Tuy nhiên, đáng chú ý là một số ngôn ngữ, như Python, cung cấp hỗ trợ trực quan hơn cho số phức thông qua các kiểu dữ liệu tích hợp và bộ thư viện phong phú hơn. Mặc dù vậy, hiệu suất và kiểm soát mà C cung cấp khiến nó trở thành lựa chọn ưa thích cho các nhiệm vụ tính toán hiệu suất cao, ngay cả khi điều này có nghĩa là phải đối mặt với cú pháp tương đối dài dòng hơn cho số học phức.
