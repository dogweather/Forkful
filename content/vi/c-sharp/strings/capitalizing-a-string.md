---
title:                "Viết hoa một chuỗi"
aliases:
- /vi/c-sharp/capitalizing-a-string/
date:                  2024-01-28T21:56:04.715646-07:00
model:                 gpt-4-0125-preview
simple_title:         "Viết hoa một chuỗi"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/c-sharp/capitalizing-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Chuyển một chuỗi thành chữ hoa trong lập trình nghĩa là làm cho tất cả các chữ cái trong một chuỗi thành chữ hoa. Đây là một tác vụ phổ biến để định dạng đầu ra, cải thiện khả năng đọc hoặc chuẩn bị dữ liệu cho việc so sánh hoặc bảo quản nhất quán.

## Làm thế nào:

Trong C#, bạn có thể chuyển một chuỗi thành chữ hoa sử dụng phương thức `ToUpper` trên một thể hiện của chuỗi. Dưới đây là cách làm:

```C#
string original = "hello world!";
string capitalized = original.ToUpper();

Console.WriteLine(capitalized); // Đầu ra: HELLO WORLD!
```

Chỉ đơn giản như vậy - chuỗi của bạn giờ đây đang "hét" lên ở dạng chữ hoa.

## Tìm hiểu sâu hơn

Việc viết hoa không phải là một phát minh hiện đại. Trên thực tế, các bản thảo cổ thường bắt đầu bằng những chữ cái đầu lớn, trang trí, mà còn được gọi là capitulum, hoặc chữ cái viết hoa. Tiến lên phía trước đến kỷ nguyên máy tính: viết hoa đóng vai trò thực tế, như làm cho tiêu đề nổi bật hơn hoặc đảm bảo so sánh không phụ thuộc vào kí tự hoa thường.

Trong khi `.ToUpper()` khá đơn giản, hãy nhận thức được về những lựa chọn thay thế và những điều đặc biệt:

1. **Nhạy cảm với Văn Hóa**: Theo mặc định, `ToUpper()` sử dụng quy tắc chữ hoa của văn hóa hiện tại. Nếu bạn cần một kết quả không phụ thuộc vào văn hóa, sử dụng `ToUpperInvariant()`.

2. **Hiệu Suất**: Việc liên tục chuyển chuỗi thành chữ hoa có thể tốn kém, đặc biệt là trong các vòng lặp. Hãy chú ý đến việc chuyển đổi không cần thiết.

3. **Các Lựa Chọn Thay Thế**: Cũng có `ToLower()`, cho hiệu ứng ngược lại (chuyển một chuỗi thành chữ thường), và `TextInfo.ToTitleCase()`, để viết hoa chỉ chữ cái đầu tiên của mỗi từ.

4. **Thực Hành Bảo Mật**: Hãy cẩn thận với những biến đổi có hậu quả về bảo mật. Ví dụ, việc so sánh mật khẩu luôn nên phụ thuộc vào kí tự hoa thường để duy trì độ phức tạp.

Dưới đây là cách bạn viết hoa đồng thời không phụ thuộc văn hóa:

```C#
string original = "iççe";
string capitalizedInvariant = original.ToUpperInvariant();

Console.WriteLine(capitalizedInvariant); // Đầu ra: İÇÇE
```

Chú ý rằng dấu chấm trên 'i' vẫn còn sau khi viết hoa theo quy tắc văn hóa không phụ thuộc.

## Xem thêm:

- Tài liệu chính thức của Microsoft về `.ToUpper()`:
  [MSDN - Phương thức String.ToUpper](https://docs.microsoft.com/en-us/dotnet/api/system.string.toupper)
  
- Giới thiệu về CultureInfo:
  [MSDN - Lớp CultureInfo](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo)

- Thực hành tốt nhất cho việc sử dụng chuỗi trong .NET:
  [MSDN - Thực hành tốt nhất cho việc sử dụng chuỗi trong .NET](https://docs.microsoft.com/en-us/dotnet/standard/base-types/best-practices-strings)
