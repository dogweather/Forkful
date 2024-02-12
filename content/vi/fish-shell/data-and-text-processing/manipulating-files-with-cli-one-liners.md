---
title:                "Thao tác với các tệp tin bằng các lệnh CLI chỉ một dòng"
aliases:
- vi/fish-shell/manipulating-files-with-cli-one-liners.md
date:                  2024-01-28T22:04:07.022044-07:00
model:                 gpt-4-0125-preview
simple_title:         "Thao tác với các tệp tin bằng các lệnh CLI chỉ một dòng"

tag:                  "Data and Text Processing"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/fish-shell/manipulating-files-with-cli-one-liners.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì & Tại sao?

Trong lĩnh vực lập trình, đặc biệt là khi làm việc với môi trường Linux hoặc Unix, việc thao tác tệp tin trực tiếp từ giao diện dòng lệnh (CLI) không chỉ là vấn đề tiện lợi - đó là công cụ mạnh mẽ. Nhờ vào Fish Shell, với cú pháp hiện đại và các tiện ích của nó, bạn có thể biến đổi, di chuyển, hoặc phân tích tệp tin của mình với sự nhanh nhẹn và chính xác. Đó là về việc làm nhiều hơn với ít hơn, tổ chức quy trình một cách gọn nhẹ và tận dụng sức mạnh của dòng lệnh cho quản lý tệp tin hiệu quả.

## Cách thực hiện:

Thao tác tệp tin trong Fish Shell vừa trực quan vừa mạnh mẽ. Dưới đây là một số ví dụ để thể hiện khả năng của nó:

1. **Tạo tệp tin** đơn giản như bạn mong đợi. Sử dụng lệnh `touch`:

```Fish Shell
touch myfile.txt
```

Lệnh này tạo ra một tệp tin trống tên là `myfile.txt`.

2. **Viết văn bản vào tệp tin** có thể được thực hiện với lệnh `echo` kết hợp với toán tử chuyển hướng:

```Fish Shell
echo "Hello, Fish Shell!" > hello.txt
```

Điều này sẽ viết "Hello, Fish Shell!" vào tệp tin `hello.txt`, ghi đè lên nội dung của nó.

3. **Thêm văn bản vào tệp tin** mà không xóa nội dung trước đó sử dụng `>>`:

```Fish Shell
echo "Another line." >> hello.txt
```

Bây giờ `hello.txt` chứa hai dòng văn bản.

4. **Đọc nội dung tệp tin** đơn giản với `cat`:

```Fish Shell
cat hello.txt
```

Đầu ra:
```
Hello, Fish Shell!
Another line.
```

5. **Tìm kiếm tệp tin** sử dụng lệnh `find` cho phép áp dụng các mẫu tìm kiếm mạnh mẽ. Để tìm tất cả tệp `.txt` trong thư mục hiện tại và các thư mục con:

```Fish Shell
find . -type f -name "*.txt"
```

6. **Đổi tên hàng loạt** có thể được xử lý một cách tinh tế với một vòng lặp. Dưới đây là đoạn mã đơn giản để thêm tiền tố `new_` cho tất cả các tệp `.txt`:

```Fish Shell
for file in *.txt
    mv $file "new_$file"
end
```

7. **Xóa tệp tin** được thực hiện với `rm`. Để xóa tất cả các tệp `.txt` một cách an toàn với một lời nhắc trước mỗi lần xóa:

```Fish Shell
for file in *.txt
    rm -i $file
end
```

## Sâu hơn

Thao tác tệp tin từ CLI với các lệnh một dòng trong Fish Shell vừa là một kỹ năng vừa là một nghệ thuật. Về mặt lịch sử, các hệ thống Unix và Linux luôn cung cấp một bộ công cụ mạnh mẽ cho việc thao tác tệp tin, coi mọi thứ như một tệp tin theo triết lý của nó. Điều này đã mở đường cho các shell hiện đại như Fish, không chỉ chấp nhận mà còn mở rộng những triết lý này với cú pháp được cải thiện và các tiện ích được thêm vào.

Mặc dù Fish cung cấp một trải nghiệm người dùng xuất sắc và khả năng viết kịch bản, đáng chú ý là một số vấn đề về tuân thủ POSIX có thể xảy ra, đặc biệt là khi các kịch bản được chuyển từ các shell truyền thống như Bash hoặc SH. Điều này là do Fish không nhằm mục đích tuân thủ POSIX theo thiết kế, thay vào đó chọn một cách tiếp cận thân thiện hơn với người dùng cả trong viết kịch bản và sử dụng dòng lệnh. Do đó, các lập trình viên nên biết rằng mặc dù Fish xuất sắc ở nhiều lĩnh vực, các kịch bản yêu cầu tuân thủ POSIX chặt chẽ có thể cần được điều chỉnh hoặc cần có các giải pháp thay thế như `bash` hoặc `zsh` để tương thích.

Các lựa chọn thay thế cho Fish để thao tác tệp tin bao gồm Bash và Zsh đã được nhắc đến, nhưng còn có awk, sed và Perl, mỗi công cụ có điểm mạnh và đường cong học tập riêng. Sự lựa chọn thường phụ thuộc vào yêu cầu cụ thể của công việc, sở thích cá nhân, và nhu cầu về khả năng tương thích giữa các shell.

Trong việc thực thi thao tác tệp tin, việc hiểu rõ các chi tiết thực hiện cụ thể về cách Fish xử lý luồng tệp tin, chuyển hướng, và thực thi lệnh có thể trao quyền cho các nhà phát triển viết các kịch bản hiệu quả và mạnh mẽ hơn. Kiến thức này cũng hỗ trợ trong quá trình gỡ lỗi và tối ưu hóa các hoạt động tệp tin cho các yêu cầu quy mô lớn hoặc yêu cầu hiệu suất cao.

Kết luận, dù Fish Shell cung cấp một giao diện mạnh mẽ và thân thiện với người dùng để thao tác tệp tin, việc cân nhắc các tính năng sáng tạo của nó so với nhu cầu về tính di động và tuân thủ trong các tình huống rộng lớn hơn là điều cần thiết.
