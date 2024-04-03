---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:07:52.171316-07:00
description: '#'
lastmod: '2024-03-13T22:44:36.746561-06:00'
model: gpt-4-0125-preview
summary: '#.'
title: "T\xECm ki\u1EBFm v\xE0 thay th\u1EBF v\u0103n b\u1EA3n"
weight: 10
---

### Điều gì và Tại sao?
Tìm và thay thế văn bản là cách bạn tìm các chuỗi cụ thể trong nội dung và thay thế chúng bằng thứ khác. Lập trình viên làm điều này để cập nhật dữ liệu, sửa lỗi hoặc thay đổi văn bản hàng loạt mà không cần chỉnh sửa thủ công.

### Cách thực hiện:
Dưới đây là cách nhanh chóng để thay thế 'cat' bằng 'dog' trong một câu sử dụng PHP:

```PHP
<?php
$text = 'The quick brown fox jumps over the lazy cat';
$replacedText = str_replace('cat', 'dog', $text);

echo $replacedText;
?>
```

Kết quả hiển thị:

```
The quick brown fox jumps over the lazy dog
```

Giờ, giả sử chúng ta đang xử lý thay thế không phân biệt chữ hoa chữ thường:

```PHP
<?php
$text = 'Catapults are CATegorically amazing!';
$replacedText = str_ireplace('cat', 'dog', $text);

echo $replacedText;
?>
```

Kết quả hiển thị:

```
Dogapults are DOGegorically amazing!
```

### Sâu hơn nữa:
Chức năng tìm kiếm và thay thế đã tồn tại từ những ngày đầu tiên của máy tính - nghĩ về `sed` trong Unix. Trong PHP, `str_replace` và `str_ireplace` là những lựa chọn của bạn cho việc tìm kiếm và thay thế đơn giản. `str_replace` phân biệt chữ hoa chữ thường, trong khi `str_ireplace` thì không.

Chúng hoạt động như thế nào? Cơ bản, cả hai hàm đều kiểm tra từng phần của chuỗi, tìm kiếm các trùng khớp và thay thế chúng. Chúng còn xử lý mảng, vì vậy bạn có thể tìm kiếm và thay thế nhiều mẫu trong một lần chạy.

Bây giờ, nếu bạn cần nhiều kiểm soát hơn, như phù hợp với mẫu, bạn sẽ muốn sử dụng `preg_replace`. Hàm này sử dụng biểu thức chính quy, cung cấp nhiều linh hoạt và chính xác hơn:

```PHP
<?php
$text = 'The quick brown fox jumps over the lazy cat 7 times.';
$replacedText = preg_replace('/\bcat\b/i', 'dog', $text);

echo $replacedText;
?>
```

Kết quả hiển thị:

```
The quick brown fox jumps over the lazy dog 7 times.
```

Lần này, 'cat' được thay thế bằng 'dog', bỏ qua chữ hoa chữ thường (`/i` chỉ báo), và chỉ khớp với từ nguyên (`\b` biên giới từ).

### Xem thêm:
- Tài liệu chính thức của PHP về str_replace: https://www.php.net/manual/en/function.str-replace.php
- Tài liệu chính thức của PHP về str_ireplace: https://www.php.net/manual/en/function.str-ireplace.php
- Tài liệu chính thức của PHP về preg_replace: https://www.php.net/manual/en/function.preg-replace.php
- Hướng dẫn về Biểu thức Chính quy: https://www.regular-expressions.info/
- Biên tập viên dòng lệnh `sed` trong Unix cho việc lọc và biến đổi văn bản: http://www.grymoire.com/Unix/Sed.html
