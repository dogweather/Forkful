---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:11:30.800253-07:00
description: ''
lastmod: '2024-03-13T22:44:36.905144-06:00'
model: gpt-4-0125-preview
summary: .
title: "L\xE0m vi\u1EC7c v\u1EDBi YAML"
weight: 41
---

## Cái gì & Tại sao?
YAML ain't Markup Language (YAML) là một tiêu chuẩn mã hóa dữ liệu được con người có thể đọc. Lập trình viên sử dụng nó cho các tập tin cấu hình, lưu trữ dữ liệu, và tin nhắn giữa các quy trình do sự đơn giản và tính dễ đọc của nó.

## Làm thế nào:
Dưới đây là một ví dụ đơn giản về việc đọc một tập tin YAML sử dụng Bash.

Cho biết `config.yaml`:
```yaml
database:
  host: localhost
  port: 3306
  username: user
  password: pass123
```

Sử dụng script này để đọc YAML và in ra host của cơ sở dữ liệu:

```Bash
#!/bin/bash
value=$(grep 'host:' config.yaml | awk '{ print $2 }')
echo "Host Cơ sở dữ liệu: ${value}"
```

Kết quả mẫu:
```
Host Cơ sở dữ liệu: localhost
```

## Thảo luận sâu hơn
YAML, được tạo ra vào năm 2001, là một lựa chọn thân thiện hơn với con người so với XML hoặc JSON. Nó được sử dụng rộng rãi trong các dịch vụ đám mây, triển khai ứng dụng và các công cụ devops. Mặc dù Bash không hỗ trợ phân tích cú pháp YAML tự nhiên, nhưng các công cụ như `yq` và phân tích cú pháp qua `awk` hoặc `grep` có thể giải quyết công việc. Tuy nhiên, việc phân tích cú pháp phức tạp có thể cần đến công cụ YAML chính xác.

## Tham khảo thêm
- Trang web chính thức của YAML: https://yaml.org
- `yq`, một bộ xử lý YAML dòng lệnh: https://github.com/kislyuk/yq
- Thảo luận về phân tích cú pháp YAML bằng Bash: https://stackoverflow.com/questions/5014632/how-can-i-parse-a-yaml-file-from-a-linux-shell-script
