---
title:                "Tải về một trang web"
aliases:
- /vi/vba/downloading-a-web-page/
date:                  2024-02-01T21:53:08.841588-07:00
model:                 gpt-4-0125-preview
simple_title:         "Tải về một trang web"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/vba/downloading-a-web-page.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái Gì & Tại Sao?

Tải một trang web bằng Visual Basic for Applications (VBA) bao gồm việc lấy nội dung HTML của một trang web từ Internet. Các lập trình viên thường thực hiện công việc này để xử lý hoặc phân tích nội dung của các trang web một cách lập trình, từ trong Excel, Access, hoặc các ứng dụng Office khác.

## Làm Thế Nào:

Để tải một trang web trong VBA, bạn có thể sử dụng thư viện Microsoft XML, v6.0 (MSXML6), cho phép thực hiện các yêu cầu HTTP đến máy chủ. Trước khi đi sâu vào code, hãy đảm bảo bạn đã kích hoạt tham chiếu này trong trình chỉnh sửa VBA bằng cách vào `Công Cụ` -> `Tham Chiếu` và kiểm tra `Microsoft XML, v6.0`.

Dưới đây là một ví dụ đơn giản về cách tải nội dung HTML của một trang web:

```basic
Sub DownloadWebPage()
    Dim request As Object
    Dim url As String
    Dim response As String
    
    ' Khởi tạo đối tượng yêu cầu XML HTTP
    Set request = CreateObject("MSXML2.XMLHTTP")
    
    url = "http://www.example.com"
    
    ' Mở một yêu cầu đồng bộ
    request.Open "GET", url, False
    
    ' Gửi yêu cầu đến máy chủ
    request.send
    
    ' Nhận văn bản phản hồi
    response = request.responseText
    
    ' Xuất phản hồi ra cửa sổ ngay lập tức (để mục đích gỡ lỗi)
    Debug.Print response
    
    ' Dọn dẹp
    Set request = Nothing
End Sub
```

Chạy subroutine này sẽ in HTML của `http://www.example.com` ra Cửa Sổ Ngay Lập Tức trong trình chỉnh sửa VBA. Lưu ý là tham số `False` trong phương thức `Open` làm cho yêu cầu trở nên đồng bộ, nghĩa là code sẽ đợi cho đến khi trang web được tải xong trước khi chuyển tới dòng tiếp theo.

## Sâu Hơn

Kỹ thuật được trình bày dựa vào MSXML, triển khai của Microsoft cho chuẩn XML HTTP Request, thường được sử dụng cho các yêu cầu AJAX trong phát triển web. Thành phần này đã là một phần của ngăn xếp công nghệ của Microsoft trong một thời gian dài, làm cho nó trở thành một lựa chọn vững chắc cho các yêu cầu mạng trong VBA.

Tuy nhiên, sự phụ thuộc vào MSXML và VBA để tải và phân tích nội dung web có thể trở nên hạn chế, đặc biệt với các ứng dụng web hiện đại mà sử dụng JavaScript nhiều cho việc hiển thị nội dung động. Những hạn chế này có thể làm cho các ngôn ngữ hoặc công cụ khác như Python với các thư viện như BeautifulSoup hoặc Selenium trở nên phù hợp hơn cho các tác vụ lấy dữ liệu từ web do khả năng thực thi JavaScript và xử lý các tương tác phức tạp trên trang web.

Dù vậy, đối với những công việc đơn giản liên quan đến việc lấy nội dung HTML đơn giản hoặc khi làm việc trong giới hạn của các ứng dụng Office, VBA vẫn là một công cụ thực tiễn. Sự tích hợp của nó trong bộ Office cho phép thao tác trực tiếp với các tài liệu dựa trên nội dung web, cung cấp một lợi thế độc đáo cho các trường hợp sử dụng cụ thể.
