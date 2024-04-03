---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:06:25.230841-07:00
description: "T\xE1i c\u1EA5u tr\xFAc l\xE0 qu\xE1 tr\xECnh ch\u1EC9nh s\u1EEDa m\xE3\
  \ ngu\u1ED3n c\u1EE7a b\u1EA1n m\xE0 kh\xF4ng thay \u0111\u1ED5i h\xE0nh vi b\xEA\
  n ngo\xE0i c\u1EE7a n\xF3. \u0110\xF3 t\u1EA5t c\u1EA3 l\xE0 v\u1EC1 vi\u1EC7c d\u1ECD\
  n d\u1EB9p v\xE0 t\u1ED5 ch\u1EE9c l\u1EA1i c\xF4ng vi\u1EC7c c\u1EE7a\u2026"
lastmod: '2024-03-13T22:44:36.723284-06:00'
model: gpt-4-0125-preview
summary: "T\xE1i c\u1EA5u tr\xFAc l\xE0 qu\xE1 tr\xECnh ch\u1EC9nh s\u1EEDa m\xE3\
  \ ngu\u1ED3n c\u1EE7a b\u1EA1n m\xE0 kh\xF4ng thay \u0111\u1ED5i h\xE0nh vi b\xEA\
  n ngo\xE0i c\u1EE7a n\xF3."
title: "T\xE1i c\u1EA5u tr\xFAc m\xE3"
weight: 19
---

## Làm thế nào:
Giả sử bạn có một khối mã Haskell đang lặp lại nhiều hơn bài hát yêu thích của bạn. Dưới đây là cái nhìn nhanh về cách bạn có thể tái cấu trúc điều đó bằng cách sử dụng các hàm.

Trước khi tái cấu trúc:

```haskell
printInvoice :: String -> Float -> String -> IO ()
printInvoice customer total item = do
  putStrLn $ "Khách hàng: " ++ customer
  putStrLn $ "Tổng cộng: " ++ show total
  putStrLn $ "Mặt hàng: " ++ item
```

Sau một chút tái cấu trúc:

```haskell
printDetail :: String -> String -> IO ()
printDetail label value = putStrLn $ label ++ ": " ++ value

printInvoice :: String -> Float -> String -> IO ()
printInvoice customer total item = do
  printDetail "Khách hàng" customer
  printDetail "Tổng cộng" (show total)
  printDetail "Mặt hàng" item

-- Đầu ra mẫu:
-- Khách hàng: Alice
-- Tổng cộng: $42.00
-- Mặt hàng: Hướng dẫn Lập trình Haskell
```

Như bạn có thể thấy, bằng cách trích xuất mẫu chung vào một hàm `printDetail` riêng biệt, chúng ta tránh được việc lặp lại và làm cho `printInvoice` rõ ràng và dễ quản lý hơn.

## Sâu hơn nữa
Khi Haskell xuất hiện vào cuối những năm 80, rõ ràng là mô hình hàm có thể mang lại làn gió mới cho các thực hành lập trình. Thời gian trôi qua, và tái cấu trúc trong Haskell đặc biệt thanh lịch nhờ vào việc các hàm là công dân hạng nhất và hệ thống kiểu mạnh mẽ của nó. Bạn tái cấu trúc mà không lo sợ sẽ làm hỏng ứng dụng của mình vì biên dịch viên đã hỗ trợ bạn.

Các phương án thay thế cho việc tái cấu trúc thủ công có thể bao gồm sử dụng các công cụ tự động, mặc dù bản chất hàm và an toàn kiểu của Haskell đôi khi khiến điều này ít phổ biến hơn so với các ngôn ngữ khác. Về mặt thực hiện, điều quan trọng là tận dụng các tính năng của Haskell như hàm bậc cao, tính tinh khiết và bất biến để làm cho việc tái cấu trúc trở nên mượt mà hơn.

Các tái cấu trúc như "Trích xuất Hàm", vừa được trình bày, là phổ biến, nhưng bạn cũng có thể thực hiện "Chèn Hàm", "Đổi tên Biến", và "Thay đổi Chữ ký Hàm" một cách tự tin, nhờ vào hệ thống kiểu. Sự suy luận kiểu mạnh mẽ của Haskell đôi khi có thể bắt được lỗi mà có thể trượt qua trong các ngôn ngữ khác.

## Xem thêm
Để tìm hiểu sâu hơn về tái cấu trúc trong Haskell, hãy tham khảo sách "Refactoring: Cải thiện Thiết kế của Mã Nguồn Hiện Tại" của Martin Fowler, nơi các khái niệm được áp dụng một cách phổ quát. Thử nghiệm công cụ hlint để nhận gợi ý tự động về cách cải thiện mã Haskell của bạn. Cũng đừng quên ghé qua wiki Haskell (https://wiki.haskell.org/Refactoring) để biết thêm thông tin từ cộng đồng và tài liệu đọc thêm.
