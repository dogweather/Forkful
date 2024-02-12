---
title:                "Làm việc với TOML"
aliases:
- vi/elixir/working-with-toml.md
date:                  2024-01-28T22:10:59.309568-07:00
model:                 gpt-4-0125-preview
simple_title:         "Làm việc với TOML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/elixir/working-with-toml.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Điều gì & Tại sao?
Làm việc với TOML có nghĩa là phân tích và tạo dữ liệu TOML (Tom's Obvious, Minimal Language - Ngôn ngữ Tối giản, Hiển nhiên của Tom) bằng Elixir. Lập trình viên sử dụng nó để xử lý các tệp cấu hình vì TOML dễ đọc, dễ phân tích và ánh xạ tốt với cấu trúc dữ liệu hash.

## Làm thế nào:
Đầu tiên, thêm một bộ phân tích TOML vào các phụ thuộc mix của bạn. Ví dụ này sử dụng `toml-elixir`:

```elixir
def deps do
  [
    {:toml_elixir, "~> 2.0"}
  ]
end
```

Đọc một tệp TOML:

```elixir
{:ok, toml_data} = File.read("config.toml")
{:ok, parsed_data} = TomlElixir.parse(toml_data)
```

Để chuyển đổi dữ liệu Elixir thành TOML:

```elixir
data = %{title: "Ví dụ TOML", owner: %{name: "Tom Preston-Werner"}}
toml_string = TomlElixir.encode(data)
```

Dữ liệu mẫu:

```elixir
"title = \"Ví dụ TOML\"\n\n[owner]\nname = \"Tom Preston-Werner\"\n"
```

## Khám phá sâu hơn
TOML được tạo ra bởi Tom Preston-Werner, đồng sáng lập của GitHub, để sử dụng trong các tệp cấu hình. Nó được thiết kế để dễ hiểu hơn XML và ngắn gọn hơn YAML trong khi vẫn giữ được sự nhất quán.

Các lựa chọn thay thế bao gồm các tệp JSON, YAML và INI, mỗi loại có những điểm đánh đổi trong đọc hiểu của con người và khả năng tương thích cấu trúc dữ liệu. TOML nổi bật trong việc biểu diễn rõ ràng dữ liệu bảng và nhóm lồng nhau của dữ liệu.

Trong Elixir, việc xử lý TOML phụ thuộc vào các thư viện mã hóa và giải mã, chuyển đổi chuỗi TOML thành các bản đồ Elixir và ngược lại. Việc phân tích hoạt động bằng cách khớp các quy tắc cú pháp của TOML và chuyển đổi chúng thành các loại dữ liệu của Elixir. Mã hóa thực hiện ngược lại bằng cách ánh xạ các loại dữ liệu của Elixir trở lại thành cú pháp TOML hợp lệ.

## Xem thêm
- Ngôn ngữ TOML: https://toml.io/en/
- Kho GitHub của `toml-elixir`: https://github.com/bitwalker/toml-elixir
- Chi tiết gói Hex cho `toml-elixir`: https://hex.pm/packages/toml_elixir
