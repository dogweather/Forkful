---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:03:18.621551-07:00
description: "Logging l\xE0 qu\xE1 tr\xECnh ghi l\u1EA1i c\xE1c s\u1EF1 ki\u1EC7n,\
  \ l\u1ED7i v\xE0 c\xE1c th\xF4ng tin \u0111\xE1ng ch\xFA \xFD kh\xE1c trong qu\xE1\
  \ tr\xECnh th\u1EF1c thi c\u1EE7a m\u1ED9t ch\u01B0\u01A1ng tr\xECnh v\xE0o m\u1ED9\
  t ph\u01B0\u01A1ng ti\u1EC7n ngo\u1EA1i vi,\u2026"
lastmod: '2024-03-13T22:44:36.327515-06:00'
model: gpt-4-0125-preview
summary: "Logging l\xE0 qu\xE1 tr\xECnh ghi l\u1EA1i c\xE1c s\u1EF1 ki\u1EC7n, l\u1ED7\
  i v\xE0 c\xE1c th\xF4ng tin \u0111\xE1ng ch\xFA \xFD kh\xE1c trong qu\xE1 tr\xEC\
  nh th\u1EF1c thi c\u1EE7a m\u1ED9t ch\u01B0\u01A1ng tr\xECnh v\xE0o m\u1ED9t ph\u01B0\
  \u01A1ng ti\u1EC7n ngo\u1EA1i vi, th\u01B0\u1EDDng l\xE0 c\xE1c t\u1EC7p ho\u1EB7\
  c c\u01A1 s\u1EDF d\u1EEF li\u1EC7u."
title: Ghi log
weight: 17
---

## Cách thức:
Trong TypeScript, bạn có thể dễ dàng triển khai logging cơ bản bằng cách sử dụng các phương thức console hoặc tích hợp logging nâng cao hơn với các thư viện như `winston` hoặc `pino`. Dưới đây là một ví dụ cơ bản sử dụng `console.log` và một ví dụ nâng cao hơn với `winston`.

```TypeScript
// Logging cơ bản với console
console.log('Thông tin: Khởi động ứng dụng...');
console.error('Lỗi: Không thể truy xuất dữ liệu.');

// Mẫu Đầu ra
// Thông tin: Khởi động ứng dụng...
// Lỗi: Không thể truy xuất dữ liệu.
```

Để log một cách mạnh mẽ hơn, hãy thiết lập `winston`:

```TypeScript
import { createLogger, format, transports } from 'winston';

const logger = createLogger({
  level: 'info',
  format: format.combine(
    format.timestamp({ format: 'YYYY-MM-DD HH:mm:ss' }),
    format.printf(info => `${info.timestamp} ${info.level}: ${info.message}`)
  ),
  transports: [
    new transports.Console(),
    new transports.File({ filename: 'combined.log' })
  ]
});

logger.info('Máy chủ đã khởi động!');
logger.warn('Cảnh báo không gian đĩa thấp.');
logger.error('Không thể kết nối với cơ sở dữ liệu.');

// Mẫu Đầu ra trong combined.log
// 2023-01-20 14:42:07 info: Máy chủ đã khởi động!
// 2023-01-20 14:42:09 warn: Cảnh báo không gian đĩa thấp.
// 2023-01-20 14:42:12 error: Không thể kết nối với cơ sở dữ liệu.
```

## Khám Phá Sâu:
Khái niệm về logging trong ngữ cảnh máy tính có từ những ngày đầu của lập trình, nơi mà thuật ngữ này được xuất phát từ "sổ nhật ký" (logbook), một hệ thống ghi chép hàng hải. Lịch sử, các sự kiện chương trình thường được logged vào các bản in vật lý hoặc đầu ra terminal, đặc biệt là trong kỷ nguyên mainframe.

Nhanh chóng chuyển tới ngày nay, và bạn có một lượng lớn công cụ và thư viện tùy ý sử dụng phục vụ cho các nhu cầu logging đa dạng, từ các tệp văn bản đơn giản đến các hệ thống quản lý log phức tạp. Các lựa chọn thay thế cho `winston` bao gồm `pino`, được ca ngợi về hiệu suất cao, và `Bunyan`, dựa trên JSON. Khi làm việc với Node.js, các thư viện logging thường cung cấp cơ chế luồng để định hướng log đến các điểm đến khác nhau, hỗ trợ cho việc xoay vòng log và các bộ định dạng tùy chỉnh.

Về mặt triển khai, thông điệp log thường chứa một dấu thời gian, một mức độ nghiêm trọng (như info, warn, error), và thông điệp thực tế. Thực hành logging tốt đề xuất phân loại đúng mức độ log, tránh dữ liệu nhạy cảm trong log, và xem xét tới hậu quả về hiệu suất trong các ứng dụng có lưu lượng cao.

## Xem Thêm:
- [Winston - Một logger cho hầu như mọi thứ](https://www.npmjs.com/package/winston)
- [Pino - Logger Node.js với hiệu suất cực kỳ thấp](https://www.npmjs.com/package/pino)
- [Phương pháp Logging tốt nhất với Node.js](https://thisdavej.com/using-winston-a-versatile-logging-library-for-node-js/)
- [Ứng dụng 12 yếu tố - Logs](https://12factor.net/logs)
