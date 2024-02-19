---
aliases:
- /vi/elixir/generating-random-numbers/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:01:15.549819-07:00
description: "Vi\u1EC7c sinh s\u1ED1 ng\u1EABu nhi\xEAn trong Elixir l\xE0 m\u1ED9\
  t nhi\u1EC7m v\u1EE5 l\u1EADp tr\xECnh c\u01A1 b\u1EA3n, quan tr\u1ECDng cho c\xE1\
  c \u1EE9ng d\u1EE5ng c\u1EA7n k\u1EBFt qu\u1EA3 kh\xF4ng d\u1EF1 \u0111o\xE1n tr\u01B0\
  \u1EDBc nh\u01B0 trong vi\u1EC7c t\u1EA1o\u2026"
lastmod: 2024-02-18 23:08:50.363768
model: gpt-4-0125-preview
summary: "Vi\u1EC7c sinh s\u1ED1 ng\u1EABu nhi\xEAn trong Elixir l\xE0 m\u1ED9t nhi\u1EC7\
  m v\u1EE5 l\u1EADp tr\xECnh c\u01A1 b\u1EA3n, quan tr\u1ECDng cho c\xE1c \u1EE9\
  ng d\u1EE5ng c\u1EA7n k\u1EBFt qu\u1EA3 kh\xF4ng d\u1EF1 \u0111o\xE1n tr\u01B0\u1EDB\
  c nh\u01B0 trong vi\u1EC7c t\u1EA1o\u2026"
title: "Sinh s\u1ED1 ng\u1EABu nhi\xEAn"
---

{{< edit_this_page >}}

## Gì và Tại sao?

Việc sinh số ngẫu nhiên trong Elixir là một nhiệm vụ lập trình cơ bản, quan trọng cho các ứng dụng cần kết quả không dự đoán trước như trong việc tạo token bảo mật, lấy mẫu dữ liệu hoặc trong các thuật toán trò chơi. Các lập trình viên sử dụng nó để đưa vào một mức độ ngẫu nhiên và biến thiên trong ứng dụng của họ, làm cho chúng trở nên động hơn và ít định trước hơn.

## Làm sao:

Để sinh số ngẫu nhiên trong Elixir, bạn chủ yếu sử dụng module `:rand` mà cung cấp một số chức năng cho mục đích này. Dưới đây là hướng dẫn nhanh để bạn bắt đầu:

Đầu tiên, hãy chắc chắn bạn gieo hạt cho bộ sinh số ngẫu nhiên để khởi tạo nó với một điểm bắt đầu độc đáo:

```elixir
:rand.seed(:exsplus)
```

Để tạo một số nguyên ngẫu nhiên trong một phạm vi, sử dụng:

```elixir
random_integer = :rand.uniform(10) # Sinh một số giữa 1 và 10
IO.puts(random_integer)
```

Đối với một số thực ngẫu nhiên giữa 0 và 1.0:

```elixir
random_float = :rand.uniform()
IO.puts(random_float)
```

Bạn có thể cần một phạm vi cụ thể hơn cho số thực, yêu cầu một chút tính toán thêm:

```elixir
min = 1.5
max = 5.5
random_float_range = min + (:rand.uniform() * (max - min))
IO.puts(random_float_range)
```

Nhớ rằng, những con số này là ngẫu nhiên giả; chúng được xác định bởi hạt gieo và thuật toán nhưng đủ cho hầu hết các ứng dụng.

## Sâu hơn

Khả năng sinh số ngẫu nhiên của Elixir dựa vào module `:rand` của Erlang, phản ánh di sản và mối quan hệ chặt chẽ với Erlang. Module `:rand` đã thay thế module `:random` cũ, cung cấp các thuật toán cải tiến cho việc sinh số ngẫu nhiên. Nó cung cấp một loạt các thuật toán, mặc định là `exsplus`, nhưng cũng hỗ trợ các thuật toán khác như `exs64`, `exsl`, và nhiều hơn nữa, mỗi thuật toán có ưu và nhược điểm về tốc độ và chất lượng ngẫu nhiên.

Một khía cạnh thú vị của việc sinh số ngẫu nhiên của Elixir (và do đó là của Erlang) là cách xử lý hạt gieo. Hệ thống duy trì các trạng thái hạt riêng biệt cho từng quá trình, đảm bảo rằng các quá trình đồng thời không can thiệp vào các chuỗi số ngẫu nhiên của nhau. Điều này đặc biệt hữu ích trong các ứng dụng đồng thời, đảm bảo tính dự đoán và độ tin cậy trong các hệ thống phân tán.

Dù module `:rand` đủ sử dụng cho hầu hết các trường hợp, các ứng dụng cần số ngẫu nhiên an toàn về mặt mật mã học nên xem xét các lựa chọn khác. Module `crypto` cung cấp các chức năng như `crypto:strong_rand_bytes/1` được thiết kế để sinh dữ liệu ngẫu nhiên an toàn cho mục đích mật mã. Những lựa chọn thay thế này là cần thiết cho các ứng dụng nhạy cảm với an ninh như sinh token, mã hóa và một số loại cơ chế xác thực.
