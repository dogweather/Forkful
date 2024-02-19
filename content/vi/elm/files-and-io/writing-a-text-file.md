---
aliases:
- /vi/elm/writing-a-text-file/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:13:30.812773-07:00
description: "Vi\u1EC7c ghi m\u1ED9t t\u1EC7p v\u0103n b\u1EA3n c\xF3 ngh\u0129a l\xE0\
  \ l\u01B0u d\u1EEF li\u1EC7u trong m\u1ED9t t\u1EC7p tr\xEAn \u0111\u0129a \u1EDF\
  \ \u0111\u1ECBnh d\u1EA1ng v\u0103n b\u1EA3n. C\xE1c l\u1EADp tr\xECnh vi\xEAn th\u1EF1\
  c hi\u1EC7n \u0111i\u1EC1u n\xE0y \u0111\u1EC3 l\u01B0u tr\u1EEF d\u1EEF li\u1EC7\
  u, c\u1EA5u\u2026"
lastmod: 2024-02-18 23:08:50.624644
model: gpt-4-0125-preview
summary: "Vi\u1EC7c ghi m\u1ED9t t\u1EC7p v\u0103n b\u1EA3n c\xF3 ngh\u0129a l\xE0\
  \ l\u01B0u d\u1EEF li\u1EC7u trong m\u1ED9t t\u1EC7p tr\xEAn \u0111\u0129a \u1EDF\
  \ \u0111\u1ECBnh d\u1EA1ng v\u0103n b\u1EA3n. C\xE1c l\u1EADp tr\xECnh vi\xEAn th\u1EF1\
  c hi\u1EC7n \u0111i\u1EC1u n\xE0y \u0111\u1EC3 l\u01B0u tr\u1EEF d\u1EEF li\u1EC7\
  u, c\u1EA5u\u2026"
title: "Vi\u1EBFt m\u1ED9t t\u1EC7p v\u0103n b\u1EA3n"
---

{{< edit_this_page >}}

## Gì & Tại Sao?

Việc ghi một tệp văn bản có nghĩa là lưu dữ liệu trong một tệp trên đĩa ở định dạng văn bản. Các lập trình viên thực hiện điều này để lưu trữ dữ liệu, cấu hình, ghi nhật ký, hoặc xuất báo cáo dễ đọc cho con người.

## Làm Thế Nào:

Elm là một ngôn ngữ web ở phía trước, vì vậy nó không thể trực tiếp ghi tệp vào đĩa. Nhưng nó có thể kích hoạt một tải xuống với nội dung mong muốn. Để mô phỏng việc ghi tệp, chúng tôi sẽ tạo một văn bản và sử dụng một liên kết để tải xuống nó dưới dạng một tệp.

```Elm
module Main exposing (main)

import Browser
import Html exposing (Html, a, text, attribute)
import Html.Attributes exposing (href)

createTextFileContent : String
createTextFileContent =
    "Xin chào, Thế giới! Đây là một số nội dung."

createDownloadHref : String -> String
createDownloadHref content =
    "data:text/plain;charset=utf-8," ++ encodeURIComponent(content)

main : Html msg
main =
    a [ href (createDownloadHref createTextFileContent), attribute "download" "myTextFile.txt" ]
        [ text "Tải xuống Tệp Văn bản" ]
```

Kết quả mẫu là một liên kết có thể nhấp vào để tải xuống 'myTextFile.txt' chứa "Xin chào, Thế giới! Đây là một số nội dung."

## Đi Sâu Hơn

Elm chạy trên trình duyệt, vì vậy các hàm cần thiết để trực tiếp ghi vào hệ thống tệp không có sẵn. Lịch sử, JavaScript có những hạn chế tương tự do các hạn chế về bảo mật của trình duyệt. Tuy nhiên, các API web mới hơn và tính năng tương tác với Elm (`Cổng`) cho phép kích hoạt tải xuống hoặc xử lý truy cập hệ thống tệp trong các ứng dụng web. Các phương án khác bao gồm sử dụng ngôn ngữ lập trình phía máy chủ để thao tác tệp trực tiếp hoặc dựa vào các API web như API Truy cập Hệ thống Tệp để mở rộng khả năng trong các trình duyệt hiện đại.

## Xem Thêm

- Hướng dẫn Chính thức của Elm về Tương tác JavaScript (Cổng): [Elm Ports](https://guide.elm-lang.org/interop/ports.html)
- Web API `File` cho xử lý tệp nâng cao trong trình duyệt: [MDN Web Docs - File API](https://developer.mozilla.org/vi/docs/Web/API/File)
- Cái nhìn rộng hơn về kiến trúc Elm: [Kiến Trúc Chính thức của Elm](https://guide.elm-lang.org/architecture/)
