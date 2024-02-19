---
aliases:
- /vi/arduino/working-with-csv/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:04.439540-07:00
description: "L\xE0m vi\u1EC7c v\u1EDBi CSV (Comma-Separated Values - Gi\xE1 Tr\u1ECB\
  \ T\xE1ch Bi\u1EC7t B\u1EB1ng D\u1EA5u Ph\u1EA9y) tr\xEAn Arduino gi\xFAp b\u1EA1\
  n l\u01B0u tr\u1EEF v\xE0 qu\u1EA3n l\xFD d\u1EEF li\u1EC7u d\u01B0\u1EDBi d\u1EA1\
  ng v\u0103n b\u1EA3n. N\xF3 r\u1EBB, d\u1EC5\u2026"
lastmod: 2024-02-18 23:08:51.023895
model: gpt-4-0125-preview
summary: "L\xE0m vi\u1EC7c v\u1EDBi CSV (Comma-Separated Values - Gi\xE1 Tr\u1ECB\
  \ T\xE1ch Bi\u1EC7t B\u1EB1ng D\u1EA5u Ph\u1EA9y) tr\xEAn Arduino gi\xFAp b\u1EA1\
  n l\u01B0u tr\u1EEF v\xE0 qu\u1EA3n l\xFD d\u1EEF li\u1EC7u d\u01B0\u1EDBi d\u1EA1\
  ng v\u0103n b\u1EA3n. N\xF3 r\u1EBB, d\u1EC5\u2026"
title: "L\xE0m vi\u1EC7c v\u1EDBi CSV"
---

{{< edit_this_page >}}

## Gì và Tại Sao?
Làm việc với CSV (Comma-Separated Values - Giá Trị Tách Biệt Bằng Dấu Phẩy) trên Arduino giúp bạn lưu trữ và quản lý dữ liệu dưới dạng văn bản. Nó rẻ, dễ dàng và phổ quát, làm cho nó trở thành lý tưởng cho việc ghi dữ liệu, tệp cấu hình, hoặc giao tiếp với bảng tính và cơ sở dữ liệu.

## Làm Thế Nào:
Dưới đây là cách lưu dữ liệu cảm biến vào một tệp CSV trên thẻ SD:

```Arduino
#include <SD.h>
#include <SPI.h>

File myFile;
int sensorValue = analogRead(A0);  // giả sử giá trị cảm biến

void setup() {
  Serial.begin(9600);
  
  if (!SD.begin(4)) {  // Thẻ SD được kết nối với chân 4
    Serial.println("Thẻ SD lỗi hoặc không có mặt");
    return;
  }
  
  myFile = SD.open("data.csv", FILE_WRITE);
  
  if (myFile) {
    myFile.print("Thời Gian, Giá Trị Cảm Biến\n");
    unsigned long time = millis();
    myFile.print(time);
    myFile.print(", ");
    myFile.print(sensorValue);
    myFile.close();
    
    Serial.println("Dữ liệu đã được ghi vào thẻ SD.");
  } else {
    Serial.println("Lỗi khi mở tệp để viết.");
  }
}

void loop() {
  // Không có gì để làm ở đây
}
```

Dữ liệu CSV mẫu trong `data.csv`:
```
Thời Gian, Giá Trị Cảm Biến
12345, 678
```

## Sâu Hơn
Định dạng CSV có thể truy cứu về những ngày đầu của việc tính toán. Mặc dù có những lựa chọn tiên tiến hơn, như JSON hay XML, CSV vẫn là sự lựa chọn hàng đầu do tính đơn giản và hỗ trợ rộng rãi trên các nền tảng. Khi làm việc với Arduino, hãy nhớ về bộ nhớ hạn chế và chọn các thư viện CSV tối giản hoặc các hàm được viết riêng để phân tích và tạo dữ liệu CSV một cách hiệu quả.

## Xem Thêm
- Tài liệu tham khảo thư viện SD của Arduino: https://www.arduino.cc/en/reference/SD
- Phân tích CSV đơn giản trong C: https://github.com/robertgamble/simplecsv
- Hướng dẫn lưu dữ liệu Arduino vào Excel: https://www.instructables.com/Save-Arduino-sensor-data-to-a-text-file/
