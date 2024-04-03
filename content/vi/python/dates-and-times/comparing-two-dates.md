---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:56:59.388487-07:00
description: "So s\xE1nh hai ng\xE0y c\xF3 ngh\u0129a l\xE0 ki\u1EC3m tra ng\xE0y\
  \ n\xE0o \u0111\u1EBFn tr\u01B0\u1EDBc ho\u1EB7c ch\xFAng c\xE1ch xa nhau bao xa\
  \ v\u1EC1 th\u1EDDi gian. L\u1EADp tr\xECnh vi\xEAn l\xE0m \u0111i\u1EC1u n\xE0\
  y \u0111\u1EC3 l\xEAn l\u1ECBch cho c\xE1c s\u1EF1\u2026"
lastmod: '2024-03-13T22:44:36.113821-06:00'
model: gpt-4-0125-preview
summary: "So s\xE1nh hai ng\xE0y c\xF3 ngh\u0129a l\xE0 ki\u1EC3m tra ng\xE0y n\xE0\
  o \u0111\u1EBFn tr\u01B0\u1EDBc ho\u1EB7c ch\xFAng c\xE1ch xa nhau bao xa v\u1EC1\
  \ th\u1EDDi gian."
title: "So s\xE1nh hai ng\xE0y"
weight: 27
---

## Cách thực hiện:
Trong Python, bạn có thể sử dụng mô-đun `datetime` để so sánh các ngày. Dưới đây là cách làm:

```Python
from datetime import datetime

# Định nghĩa hai ngày
date_1 = datetime(2023, 3, 25)
date_2 = datetime(2023, 4, 1)

# So sánh các ngày
print(date_1 < date_2)    # Kết quả: True
print(date_1 > date_2)    # Kết quả: False
print(date_1 == date_2)   # Kết quả: False

# Tính khoảng cách
difference = date_2 - date_1
print(difference.days)    # Kết quả: 7
```

## Sâu xa hơn
Việc so sánh các ngày không phải là điều mới. Nó đã là chìa khóa trong các hệ thống cổ xưa như chính lịch. `Datetime` của Python chỉ là việc tiếp tục truyền thống đó một cách số hóa. Có những cách khác để so sánh các ngày như sử dụng dấu thời gian Unix, hoặc thư viện như `dateutil` cho những thành tựu phức tạp. Nhưng `datetime` là cơ bản của bạn. Nó biểu diễn các ngày như những đối tượng, cho phép so sánh trực tiếp sử dụng các toán tử so sánh (`<`, `>`, `==`, v.v.). Khi bạn trừ đi các ngày, bạn nhận được một đối tượng `timedelta`, cho biết sự khác biệt về ngày, giây, và microgiây.

Ngoài ra, múi giờ có thể làm bạn bối rối. Nếu bạn đang xử lý các ngày qua các múi giờ, bạn sẽ phải làm cho chúng nhận biết được. Python cung cấp thư viện `pytz`, có thể được sử dụng với `datetime` để xử lý múi giờ hiệu quả.

## Xem thêm:
- Tài liệu mô-đun `datetime` của Python: [docs.python.org/3/library/datetime.html](https://docs.python.org/3/library/datetime.html)
- Quản lý múi giờ: [pytz](https://pypi.org/project/pytz/)
- Thư viện `dateutil` cho việc điều chỉnh ngày phức tạp: [dateutil](https://pypi.org/project/python-dateutil/)
- Hiểu về Dấu thời gian Unix: [Thời gian Unix - Wikipedia](https://en.wikipedia.org/wiki/Unix_time)
