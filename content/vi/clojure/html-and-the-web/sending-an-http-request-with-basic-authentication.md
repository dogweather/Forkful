---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:08:13.084190-07:00
description: "G\u1EEDi m\u1ED9t y\xEAu c\u1EA7u HTTP v\u1EDBi x\xE1c th\u1EF1c c\u01A1\
  \ b\u1EA3n bao g\u1ED3m vi\u1EC7c th\xEAm t\xEAn ng\u01B0\u1EDDi d\xF9ng v\xE0 m\u1EAD\
  t kh\u1EA9u v\xE0o m\u1ED9t y\xEAu c\u1EA7u \u0111\u1EC3 truy c\u1EADp v\xE0o c\xE1\
  c t\xE0i nguy\xEAn b\u1ECB h\u1EA1n ch\u1EBF. C\xE1c l\u1EADp\u2026"
lastmod: '2024-03-13T22:44:36.152756-06:00'
model: gpt-4-0125-preview
summary: "G\u1EEDi m\u1ED9t y\xEAu c\u1EA7u HTTP v\u1EDBi x\xE1c th\u1EF1c c\u01A1\
  \ b\u1EA3n bao g\u1ED3m vi\u1EC7c th\xEAm t\xEAn ng\u01B0\u1EDDi d\xF9ng v\xE0 m\u1EAD\
  t kh\u1EA9u v\xE0o m\u1ED9t y\xEAu c\u1EA7u \u0111\u1EC3 truy c\u1EADp v\xE0o c\xE1\
  c t\xE0i nguy\xEAn b\u1ECB h\u1EA1n ch\u1EBF."
title: "G\u1EEDi m\u1ED9t y\xEAu c\u1EA7u HTTP v\u1EDBi x\xE1c th\u1EF1c c\u01A1 b\u1EA3\
  n"
weight: 45
---

## Cách thực hiện:
Trong Clojure, bạn sẽ thường sử dụng thư viện `clj-http` cho các yêu cầu HTTP, bao gồm cả những yêu cầu với xác thực cơ bản. Hãy bắt đầu bằng cách thêm dependency (`[clj-http "3.12.3"]` tính đến lần cập nhật cuối cùng của tôi) vào `project.clj` của bạn.

Tiếp theo, dưới đây là cách bạn tạo một yêu cầu GET với xác thực cơ bản:

```clojure
(require '[clj-http.client :as client])

(let [response (client/get "https://your-api.com/resource"
                           {:basic-auth ["username" "password"]})]
  (println "Trạng thái:" (:status response))
  (println "Nội dung:" (:body response)))
```
Thay `"https://your-api.com/resource"`, `"username"`, và `"password"` bằng thông tin của bạn. Mã này gửi một yêu cầu GET và in ra trạng thái và nội dung của phản hồi.

Kết quả mẫu có thể trông như thế này:

```
Trạng thái: 200
Nội dung: {Dữ liệu JSON hoặc cái gì đó khác ở đây}
```

## Sâu hơn
Xác thực cơ bản HTTP có nguồn gốc từ các giao thức web sơ khai. Nó truyền tên người dùng và mật khẩu trong một tiêu đề HTTP được mã hóa sử dụng Base64. Mặc dù nó đơn giản, nhưng không phải là an toàn nhất vì thông tin đăng nhập có thể dễ dàng được giải mã nếu bị ngắt quãng.

Các phương thức thay thế:
- **Xác thực Digest**: Phức tạp hơn, liên quan đến việc gửi một phiên bản đã được băm của mật khẩu thay vì.
- **OAuth**: Một hệ thống xác thực mạnh mẽ hơn không đòi hỏi việc gửi tên người dùng và mật khẩu.
- **Khóa API**: Token duy nhất được sử dụng thay cho thông tin đăng nhập truyền thống.

Bên dưới phần thư viện `clj-http`, chỉ định `:basic-auth` trong hashmap tùy chọn kích hoạt thư viện mã hóa thông tin đăng nhập của bạn và đính kèm chúng vào tiêu đề HTTP `Authorization`. Khi máy chủ nhận được yêu cầu, nó giải mã tiêu đề và kiểm tra thông tin đăng nhập.

Hãy nhớ rằng, để truyền tải an toàn, HTTPS nên được sử dụng để ngăn chặn người khác chặn thông tin đăng nhập của bạn.

## Xem thêm
- Kho GitHub clj-http: https://github.com/dakrone/clj-http
- Tài liệu chính thức của Clojure: https://clojure.org/
- Xác thực HTTP trên MDN: https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication 
- Hiểu về OAuth: https://oauth.net/
