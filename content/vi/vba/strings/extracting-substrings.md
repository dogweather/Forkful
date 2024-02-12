---
title:                "Trích xuất chuỗi con"
aliases:
- /vi/vba/extracting-substrings/
date:                  2024-02-01T21:54:28.515496-07:00
model:                 gpt-4-0125-preview
simple_title:         "Trích xuất chuỗi con"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/vba/extracting-substrings.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Trích xuất chuỗi con trong Visual Basic cho Ứng dụng (VBA) bao gồm việc tách ra các phần cụ thể của một chuỗi dựa trên các tiêu chí đã cho. Các lập trình viên làm điều này cho các nhiệm vụ như phân tích cú pháp dữ liệu, xác thực và định dạng, nơi mà việc thao tác và trích xuất thông tin từ dữ liệu văn bản là rất quan trọng.

## Làm thế nào:

Trong VBA, bạn chủ yếu sử dụng các hàm `Mid`, `Left`, và `Right` để trích xuất chuỗi con. Dưới đây, chúng ta khám phá các hàm này với các ví dụ:

1. **Mid**: Trích xuất một chuỗi con từ một chuỗi bắt đầu từ một vị trí cụ thể.
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Mid(exampleString, 7, 5)
   Debug.Print result  ' Kết quả: World
   ```

2. **Left**: Trích xuất một chuỗi con từ phía bên trái của chuỗi, lên đến một số lượng ký tự cụ thể.
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Left(exampleString, 5)
   Debug.Print result  ' Kết quả: Hello
   ```

3. **Right**: Trích xuất một chuỗi con từ phía bên phải của chuỗi, lên đến một số lượng ký tự cụ thể.
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Right(exampleString, 5)
   Debug.Print result  ' Kết quả: World
   ```

Những hàm cơ bản này tạo thành nền tảng của việc trích xuất chuỗi con trong VBA, cung cấp các phương thức thao tác chuỗi mạnh mẽ và dễ dàng.

## Đi sâu:

Lịch sử, khả năng thao tác với chuỗi trong lập trình đã không thể thiếu, với BASIC (tiền thân của VBA) là một trong những ngôn ngữ đầu tiên dân chủ hóa khả năng này trong những ngày đầu của máy tính cá nhân. Các hàm `Mid`, `Left`, và `Right` trong VBA kế thừa di sản này, mang lại giao diện đơn giản cho các lập trình viên hiện đại.

Mặc dù những hàm này khá hiệu quả cho nhiều nhiệm vụ, sự xuất hiện của Biểu thức Chính quy trong các ngôn ngữ mới hơn đã cung cấp một cách làm việc mạnh mẽ và linh hoạt hơn với văn bản. Dù thế, sự đơn giản và sẵn có ngay lập tức của các hàm trích xuất chuỗi con truyền thống của VBA làm cho chúng hoàn toàn phù hợp cho các nhiệm vụ nhanh chóng và những người mới học lập trình.

Đối với các nhiệm vụ phân tích cú pháp và tìm kiếm trong chuỗi phức tạp hơn, VBA cũng hỗ trợ việc so khớp mẫu thông qua toán tử `Like` và Biểu thức Chính quy thông qua đối tượng `VBScript.RegExp`, mặc dù chúng yêu cầu một chút thiết lập và hiểu biết để sử dụng hiệu quả. Mặc dù những công cụ này cung cấp sức mạnh lớn hơn, tính chất trực tiếp của `Mid`, `Left`, và `Right` đảm bảo tính liên quan và tiện ích của chúng trong nhiều chương trình VBA.
