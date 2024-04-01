---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:04:32.669741-07:00
description: "S\u1EED d\u1EE5ng m\u1ED9t tr\xECnh g\u1EE1 l\u1ED7i trong Visual Basic\
  \ for Applications (VBA) bao g\u1ED3m vi\u1EC7c ch\u1EA1y m\xE3 c\u1EE7a b\u1EA1\
  n t\u1EEBng b\u01B0\u1EDBc m\u1ED9t \u0111\u1EC3 ki\u1EC3m tra lu\u1ED3ng th\u1EF1\
  c thi v\xE0 tr\u1EA1ng th\xE1i c\u1EE7a\u2026"
lastmod: '2024-03-13T22:44:36.439108-06:00'
model: gpt-4-0125-preview
summary: "S\u1EED d\u1EE5ng m\u1ED9t tr\xECnh g\u1EE1 l\u1ED7i trong Visual Basic\
  \ for Applications (VBA) bao g\u1ED3m vi\u1EC7c ch\u1EA1y m\xE3 c\u1EE7a b\u1EA1\
  n t\u1EEBng b\u01B0\u1EDBc m\u1ED9t \u0111\u1EC3 ki\u1EC3m tra lu\u1ED3ng th\u1EF1\
  c thi v\xE0 tr\u1EA1ng th\xE1i c\u1EE7a\u2026"
title: "S\u1EED d\u1EE5ng tr\xECnh g\u1EE1 l\u1ED7i"
---

## Cách thực hiện:
Trong VBA, trình gỡ lỗi là một phần không thể thiếu của Visual Basic Editor (VBE). Dưới đây là cách bạn có thể tận dụng nó:

1. **Đặt Điểm Dừng (Breakpoints)**: Nhấp vào lề bên trái cạnh dòng mã bạn quan tâm, hoặc đặt con trỏ của bạn trên dòng đó và nhấn F9. Điều này báo cho VBA biết để tạm dừng thực thi khi nó đến điểm này.

    ```vb
    Sub DebugExample()
        Dim counter As Integer
        For counter = 1 To 5
            Debug.Print counter ' Đặt điểm dừng ở đây
        Next counter
    End Sub
    ```

    Khi mã thực thi, nó sẽ tạm dừng tại dòng `Debug.Print counter`, cho phép bạn kiểm tra giá trị của các biến.

2. **Bước vào trong (F8)**: Với lệnh này, bạn thực hiện mã của mình từng câu lệnh một lần, nhập vào bất kỳ thủ tục nào được gọi. Nó hữu ích để truy vết cách mã và các hàm tương tác với nhau.

3. **Cửa sổ Giám sát (Watch Window)**: Sử dụng Cửa sổ Giám sát để theo dõi giá trị của các biến hoặc biểu thức. Nếu một biến không nằm trong phạm vi, Cửa sổ Giám sát sẽ chỉ ra điều đó. Nhấp chuột phải vào một biến > Thêm Giám sát.

4. **Cửa sổ Lập tức (Immediate Window) (Ctrl+G)**: Cửa sổ này đặc biệt hữu ích để kiểm tra biểu thức hoặc sửa đổi giá trị biến trong khi gỡ lỗi. Gõ `?variableName` để in giá trị hiện tại của biến, hoặc gán một giá trị mới với `variableName = newValue`.

    ```vb
    ' Trong Cửa sổ Lập tức
    ?counter ' In giá trị hiện tại của counter
    counter = 3 ' Thiết lập giá trị của counter thành 3
    ```

5. **Kết quả Mẫu**:

    Khi bạn đạt đến điểm dừng và thực hiện từng dòng bằng F8, Cửa sổ Lập tức có thể hiển thị thứ gì đó như này:

    ```
    counter = 1
    counter = 2
    counter = 3
    ```

    Ở đây, chúng tôi đã thủ công truy vấn biến `counter` sau mỗi lần lặp.

## Sâu hơn nữa:
Trình gỡ lỗi trong VBA, mặc dù mạnh mẽ, là một phần của truyền thống rộng lớn hơn về các công cụ gỡ lỗi trong các ngôn ngữ lập trình, phát triển đáng kể từ những người tiền nhiệm đầu tiên của nó. Được giới thiệu với các phiên bản đầu tiên của VBA, nó nhằm mục đích cung cấp cho các nhà phát triển một bộ công cụ đơn giản nhưng mạnh mẽ để kiểm tra và sửa chữa mã. Theo thời gian, các cải tiến đã bao gồm các điểm dừng có điều kiện, khả năng giám sát được cải thiện và tích hợp với giao diện Excel cho việc kiểm tra dữ liệu trực quan hơn.

Tuy nhiên, so với các Môi trường Phát triển Tích hợp (IDE) hiện đại như Visual Studio hay Eclipse, các công cụ gỡ lỗi của VBA có thể cảm thấy cơ bản. Những IDE hiện đại này cung cấp các tính năng tinh vi hơn như kiểm tra biến thời gian thực, điểm dừng nâng cao và khung thử nghiệm đơn vị tích hợp. Mặc dù những lựa chọn thay thế này cung cấp trải nghiệm gỡ lỗi toàn diện hơn, nhưng sự đơn giản và trực tiếp của trình gỡ lỗi VBA vẫn phù hợp với bối cảnh cụ thể của tự động hóa và kịch bản trong các ứng dụng Microsoft Office.

Đối với những lập trình viên quen với những môi trường hiện đại này, việc điều chỉnh để sử dụng các công cụ gỡ lỗi của VBA có thể đòi hỏi một sự thay đổi trong cách tiếp cận. Tuy nhiên, các nguyên tắc cơ bản của việc kiểm tra biến, bước qua mã, và quan sát hành vi thời gian chạy là phổ quát. Với việc thực hành, trình gỡ lỗi của VBA trở thành một công cụ không thể thiếu để đảm bảo kịch bản tự động hóa của bạn hoạt động không lỗi lầm trong hệ sinh thái Office.
