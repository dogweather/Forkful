---
aliases:
- /vi/c-sharp/working-with-csv/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:41.641805-07:00
description: "L\xE0m vi\u1EC7c v\u1EDBi CSV (Comma-Separated Values) c\xF3 ngh\u0129\
  a l\xE0 \u0111\u1ECDc v\xE0 vi\u1EBFt d\u1EEF li\u1EC7u trong m\u1ED9t \u0111\u1ECB\
  nh d\u1EA1ng v\u0103n b\u1EA3n \u0111\u01A1n gi\u1EA3n \u2014 m\u1ED9t \u0111\u1ECB\
  nh d\u1EA1ng ph\u1ED5 bi\u1EBFn v\xE0 th\xE2n thi\u1EC7n v\u1EDBi\u2026"
lastmod: 2024-02-18 23:08:50.723172
model: gpt-4-0125-preview
summary: "L\xE0m vi\u1EC7c v\u1EDBi CSV (Comma-Separated Values) c\xF3 ngh\u0129a\
  \ l\xE0 \u0111\u1ECDc v\xE0 vi\u1EBFt d\u1EEF li\u1EC7u trong m\u1ED9t \u0111\u1ECB\
  nh d\u1EA1ng v\u0103n b\u1EA3n \u0111\u01A1n gi\u1EA3n \u2014 m\u1ED9t \u0111\u1ECB\
  nh d\u1EA1ng ph\u1ED5 bi\u1EBFn v\xE0 th\xE2n thi\u1EC7n v\u1EDBi\u2026"
title: "L\xE0m vi\u1EC7c v\u1EDBi CSV"
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Làm việc với CSV (Comma-Separated Values) có nghĩa là đọc và viết dữ liệu trong một định dạng văn bản đơn giản — một định dạng phổ biến và thân thiện với bảng tính. Lập trình viên sử dụng CSV vì sự đơn giản và khả năng tương thích khi trao đổi dữ liệu dạng bảng giữa các hệ thống.

## Làm thế nào

### Đọc File CSV
```C#
using System;
using System.IO;

class ReadCSVExample
{
    static void Main()
    {
        string path = "data.csv";
        using (var reader = new StreamReader(path))
        {
            while (!reader.EndOfStream)
            {
                var line = reader.ReadLine();
                var values = line.Split(',');
                // Bây giờ làm gì đó với giá trị, ví dụ, in chúng ra
                Console.WriteLine(String.Join(" | ", values));
            }
        }
    }
}
```
**Kết quả mẫu:**
```
John | Doe | johndoe@example.com
Jane | Smith | janesmith@example.com
```

### Viết File CSV
```C#
using System;
using System.IO;

class WriteCSVExample
{
    static void Main()
    {
        string path = "output.csv";
        var records = new[]
        {
            new[] {"Name", "Age", "Email"},
            new[] {"Alice", "23", "alice@example.com"},
            new[] {"Bob", "30", "bob@example.com"}
        };

        using (var writer = new StreamWriter(path))
        {
            foreach (var record in records)
            {
                var line = String.Join(",", record);
                writer.WriteLine(line);
            }
        }
        Console.WriteLine($"Dữ liệu đã được viết vào {path}");
    }
}
```
**Kết quả mẫu:**
```
Dữ liệu đã được viết vào output.csv
```

## Tìm hiểu sâu hơn

CSV đã xuất hiện từ những ngày đầu của ngành công nghiệp máy tính, tạo cầu nối giữa các hệ thống đa dạng. Nó không hoàn hảo — thiếu chuẩn mã hóa ký tự và không hỗ trợ tốt các trường nhiều dòng mà không có một trình phân tích cú pháp mạnh mẽ. Đó là nơi các định dạng như JSON và XML bước vào, cung cấp nhiều phức tạp hơn nhưng cấu trúc tốt hơn cho dữ liệu phân cấp.

Ở dưới cùng, bạn thường xử lý chuỗi, hoặc sử dụng các phương thức `string` có sẵn hoặc thư viện như `CsvHelper` có thể thêm sức mạnh vào việc xử lý CSV của bạn, cung cấp nhiều tính năng hơn và xử lý tình huống ngoại lệ một cách nhẹ nhàng. Nhớ lại, không có việc xử lý CSV bản địa trong .NET, vì vậy bạn tự mình xử lý chuỗi hoặc bạn có thể chọn một thư viện bên thứ ba.

## Xem thêm

Để tìm hiểu sâu hơn về việc thao tác CSV trong C#:
- [Thư viện CsvHelper](https://joshclose.github.io/CsvHelper/)
- [Tài liệu của Microsoft về `StreamReader`](https://docs.microsoft.com/en-us/dotnet/api/system.io.streamreader)

Tìm hiểu nhiều hơn về các phương án thay thế cho CSV:
- [Hiểu về JSON](https://www.json.org/json-en.html)
- [XML trong một Lõi Đậu](https://www.w3schools.com/xml/xml_whatis.asp)
