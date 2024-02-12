---
title:                "Sử dụng mảng liên kết"
aliases:
- vi/fish-shell/using-associative-arrays.md
date:                  2024-01-30T19:11:11.188314-07:00
model:                 gpt-4-0125-preview
simple_title:         "Sử dụng mảng liên kết"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/fish-shell/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?

Mảng kết hợp, hay bảng băm, cho phép bạn lưu trữ dữ liệu dưới dạng cặp khóa-giá trị, giúp việc tổ chức và truy xuất thông tin theo khóa dễ dàng hơn. Chúng rất tiện lợi khi bạn cần một cách cấu trúc hóa để xử lý dữ liệu hơn là chỉ dùng danh sách, đặc biệt trong cấu hình và khi xử lý một loạt thuộc tính.

## Làm thế nào:

Fish không hỗ trợ mảng kết hợp natively như Bash 4+, nhưng bạn có thể đạt được chức năng tương tự bằng cách sử dụng kết hợp danh sách và thao tác chuỗi. Dưới đây là cách mô phỏng chúng:

Trước tiên, thiết lập từng phần tử "mảng kết hợp" riêng lẻ:

```Fish Shell
set food_color_apple "red"
set food_color_banana "yellow"
```

Để truy cập một phần tử, chỉ cần tham chiếu trực tiếp:

```Fish Shell
echo $food_color_apple
# Kết quả: red
```

Nếu bạn cần lặp qua chúng, sử dụng vòng lặp for cùng với quy ước đặt tên:

```Fish Shell
for food in apple banana
    echo $food_color_$food
end
# Kết quả:
# red
# yellow
```

Đối với những người thiếu Bash's `${!array[@]}` để lấy tất cả khóa, bạn có thể lưu khóa trong một danh sách riêng biệt:

```Fish Shell
set food_keys apple banana

for key in $food_keys
    echo $key 'là' $food_color_$key
end
# Kết quả:
# apple là red
# banana là yellow
```

## Sâu hơn

Mảng kết hợp thực sự như trong các ngôn ngữ kịch bản khác chưa phải là một phần của cách tiếp cận của Fish. Giải pháp được hiển thị tận dụng khả năng thao tác chuỗi và danh sách của Fish để tạo ra một cấu trúc mảng kết hợp giả mạo. Mặc dù nó hoạt động, nhưng không sạch sẽ hoặc chống lỗi như sẽ có được nếu hỗ trợ mảng kết hợp được tích hợp sẵn. Các shell khác như Bash và Zsh cung cấp chức năng mảng kết hợp được tích hợp sẵn, dẫn đến mã dễ đọc, dễ hiểu hơn. Tuy nhiên, triết lý thiết kế của Fish hướng đến sự đơn giản và thân thiện với người dùng, có thể phải chịu thiệt hại bởi những tính năng đó. Giải pháp này đáp ứng hầu hết nhu cầu nhưng hãy chú ý đến sự phát triển của Fish Shell - nhóm phát triển của nó liên tục cải thiện và thêm tính năng dựa trên phản hồi từ cộng đồng.
