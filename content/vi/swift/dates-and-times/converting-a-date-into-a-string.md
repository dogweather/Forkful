---
title:                "Chuyển đổi một ngày thành chuỗi"
date:                  2024-01-28T21:57:58.895154-07:00
model:                 gpt-4-0125-preview
simple_title:         "Chuyển đổi một ngày thành chuỗi"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/swift/converting-a-date-into-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?
Việc chuyển đổi ngày tháng thành chuỗi trong Swift giúp bạn định dạng ngày tháng cho con người. Đây là chìa khóa cho việc hiển thị giao diện người dùng, ghi nhật ký, hoặc bất cứ khi nào bạn cần ngày tháng trở nên có ý nghĩa với mọi người, chứ không chỉ với code.

## Làm thế nào:
Swift sử dụng `DateFormatter` để chuyển đổi đối tượng `Date` thành chuỗi dễ đọc. Dưới đây là cách thức:

```Swift
import Foundation

let date = Date()
let formatter = DateFormatter()
formatter.dateFormat = "yyyy-MM-dd HH:mm:ss"
let dateString = formatter.string(from: date)
print(dateString) // Kết quả: "2023-04-05 14:20:35" (hoặc ngày và giờ hiện tại)
```

Thay đổi `dateFormat` để điều chỉnh cách hiển thị ngày tháng của bạn:

```Swift
formatter.dateFormat = "EEEE, MMM d, yyyy"
print(formatter.string(from: date)) // Kết quả: "Thứ Tư, Apr 5, 2023"
```

## Đào Sâu
Trước `DateFormatter`, Objective-C và phiên bản Swift đầu tiên sử dụng `NSDateFormatter`, về cơ bản là cùng một thứ được đổi tên. Điều quan trọng là biết đến ISO 8601, một tiêu chuẩn định dạng ngày tháng phổ biến. Các nhà phát triển phải cân bằng giữa các định dạng tùy chỉnh với cài đặt địa phương của người dùng. Tại sao? Bởi vì cách đọc ngày tháng khác nhau trên toàn thế giới. Ví dụ, người Mỹ sử dụng "MM/dd/yyyy", trong khi nhiều quốc gia Châu Âu sử dụng "dd/MM/yyyy".

Có phương thức thay thế không? Chắc chắn rồi. Swift cung cấp `ISO8601DateFormatter` cho các ngày tháng ISO 8601, và `DateComponentsFormatter` cho chuỗi thời lượng, như "42 phút". Bạn cũng có thể tự tạo tùy chỉnh với `.formatted()` trong Swift 5.5 trở lên:

```Swift
let formattedDate = date.formatted(.dateTime.year().month().day().hour().minute().second())
print(formattedDate) // Kết quả sẽ tùy thuộc vào cài đặt địa phương của bạn
```

Hãy cẩn trọng: Việc tạo chuỗi tùy chỉnh có thể dẫn đến nhức đầu về vấn đề địa phương hóa và code dễ xảy ra lỗi. Hãy gắn bó với các bộ định dạng và tiêu chuẩn khi có thể.

## Xem Thêm
- [Định dạng Ngày](https://developer.apple.com/documentation/foundation/dateformatter) - Tài liệu của Apple về DateFormatter
