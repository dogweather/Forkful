---
title:                "Chuyển đổi một ngày thành chuỗi"
aliases:
- /vi/google-apps-script/converting-a-date-into-a-string/
date:                  2024-02-01T21:51:56.848161-07:00
model:                 gpt-4-0125-preview
simple_title:         "Chuyển đổi một ngày thành chuỗi"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/google-apps-script/converting-a-date-into-a-string.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Việc chuyển đổi ngày tháng thành chuỗi là một nhiệm vụ cơ bản giúp các lập trình viên có thể thao tác và hiển thị thông tin ngày tháng dưới dạng có thể đọc được bởi con người. Điều này rất quan trọng để tạo giao diện người dùng, tạo báo cáo, hoặc ghi thông tin trong các ứng dụng được phát triển với Google Apps Script.

## Làm thế nào:

Google Apps Script, dựa vào JavaScript, cho phép sử dụng nhiều phương pháp khác nhau để thực hiện việc chuyển đổi ngày tháng thành chuỗi. Dưới đây là một số ví dụ minh họa các cách tiếp cận khác nhau:

### Sử dụng Phương thức `toString()`:
Phương thức đơn giản nhất là sử dụng phương thức `toString()`, chuyển đổi đối tượng ngày tháng thành chuỗi ở định dạng mặc định.

```javascript
var date = new Date();  // Tạo một đối tượng ngày tháng mới
var dateString = date.toString();
Logger.log(dateString); // Đầu ra: "Wed Apr 05 2023 12:34:56 GMT-0700 (Pacific Daylight Time)"
```

### Sử dụng Phương thức `toDateString()`:
Để chỉ lấy phần thông tin ngày tháng ở dạng đọc được mà không có thông tin thời gian, có thể sử dụng `toDateString()`.

```javascript
var date = new Date();
var dateString = date.toDateString();
Logger.log(dateString); // Đầu ra: "Wed Apr 05 2023"
```

### Sử dụng `Utilities.formatDate()` cho Định dạng Tùy chỉnh:
Để kiểm soát nhiều hơn về định dạng, Google Apps Script cung cấp `Utilities.formatDate()`. Phương pháp này yêu cầu ba tham số: đối tượng ngày tháng, múi giờ, và chuỗi định dạng.

```javascript
var date = new Date();
var timeZone = Session.getScriptTimeZone();
var formattedDate = Utilities.formatDate(date, timeZone, "YYYY-MM-dd");
Logger.log(formattedDate); // Đầu ra: "2023-04-05"
```

Phương pháp này rất mạnh mẽ để tạo ra các ngày tháng theo định dạng phù hợp với đặc thù địa phương hoặc yêu cầu cụ thể của ứng dụng.

## Tìm hiểu sâu

Nhu cầu chuyển đổi ngày tháng thành chuỗi không chỉ riêng có ở Google Apps Script; nó phổ biến trên tất cả các ngôn ngữ lập trình. Tuy nhiên, cách tiếp cận của Google Apps Script, kế thừa từ JavaScript, cung cấp một bộ tùy chọn linh hoạt dành cho lập trình dựa trên web. `Utilities.formatDate()` nổi bật bằng cách nhận biết những phức tạp khi làm việc với các múi giờ - một thách thức thường bị bỏ qua.

Trong lịch sử, việc xử lý ngày tháng và thời gian đã là nguồn gốc của nhiều lỗi và sự phức tạp trong phát triển phần mềm, chủ yếu do sự khác biệt về các múi giờ và định dạng. Việc giới thiệu `Utilities.formatDate()` trong Google Apps Script là một dấu hiệu cho sự tiêu chuẩn hóa việc xử lý ngày giờ, đặc biệt trong bối cảnh các sản phẩm của Google được sử dụng toàn cầu.

Tuy nhiên, khi cần kiểm soát chính xác về múi giờ, địa phương, và định dạng, đặc biệt trong các ứng dụng quốc tế, các nhà phát triển có thể tìm đến việc sử dụng các thư viện bên ngoài như `Moment.js` (mặc dù có sự ưa chuộng ngày càng tăng đối với `Luxon`, `Day.js`, và `date-fns` do lo ngại về kích thước gói và các tính năng hiện đại). Cách tiếp cận này, tất nhiên, đi kèm với việc thêm các phụ thuộc bên ngoài và có thể làm tăng độ phức tạp của dự án.

Dù có khả năng sử dụng các thư viện bên ngoài, `Utilities.formatDate()` và các phương thức ngày tháng bản địa của JavaScript cung cấp các giải pháp mạnh mẽ cho hầu hết các trường hợp sử dụng phổ thông. Các lập trình viên thông minh sẽ cân nhắc giữa sự đơn giản và tiện lợi của các chức năng nội bộ với sức mạnh và linh hoạt của các thư viện bên ngoài, tùy thuộc vào nhu cầu cụ thể của dự án.
