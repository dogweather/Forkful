---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:01:08.213766-07:00
description: "Vi\u1EC7c sinh s\u1ED1 ng\u1EABu nhi\xEAn trong Haskell bao g\u1ED3\
  m vi\u1EC7c t\u1EA1o ra nh\u1EEFng con s\u1ED1 kh\xF4ng th\u1EC3 d\u1EF1 \u0111\
  o\xE1n theo ti\xEAu chu\u1EA9n con ng\u01B0\u1EDDi. \u0110i\u1EC1u n\xE0y c\u1EF1\
  c k\u1EF3 quan tr\u1ECDng trong c\xE1c\u2026"
lastmod: '2024-03-13T22:44:36.707038-06:00'
model: gpt-4-0125-preview
summary: "Vi\u1EC7c sinh s\u1ED1 ng\u1EABu nhi\xEAn trong Haskell bao g\u1ED3m vi\u1EC7\
  c t\u1EA1o ra nh\u1EEFng con s\u1ED1 kh\xF4ng th\u1EC3 d\u1EF1 \u0111o\xE1n theo\
  \ ti\xEAu chu\u1EA9n con ng\u01B0\u1EDDi."
title: "Sinh s\u1ED1 ng\u1EABu nhi\xEAn"
weight: 12
---

## Làm thế nào:
Để sinh số ngẫu nhiên trong Haskell, người ta thường sử dụng gói `random`, là một phần của Haskell Platform. Dưới đây là hướng dẫn từng bước:

Đầu tiên, hãy chắc chắn rằng bạn đã cài đặt gói `random`. Nếu chưa, bạn có thể lấy nó qua Cabal hoặc Stack.

### Sinh một Số Ngẫu Nhiên
Để sinh một số ngẫu nhiên đơn giản, bạn có thể sử dụng hàm `randomRIO`, sản xuất một giá trị ngẫu nhiên trong một phạm vi xác định.

```Haskell
import System.Random (randomRIO)

main :: IO ()
main = do
  randomNumber <- randomRIO (1, 10) :: IO Int
  putStrLn $ "Số ngẫu nhiên: " ++ show randomNumber
```

### Sinh một Danh Sách Số Ngẫu Nhiên
Việc sinh một danh sách các số ngẫu nhiên hơi phức tạp hơn nhưng vẫn dễ dàng:

```Haskell
import System.Random (randomRIO)

randomList :: Int -> IO [Int]
randomList 0 = return []
randomList n = do
  r <- randomRIO (1, 100)
  rs <- randomList (n-1)
  return (r:rs)

main :: IO ()
main = do
  numbers <- randomList 5
  print numbers
```

Đoạn mã này tạo ra một hàm `randomList` mà sinh ra một danh sách các số nguyên ngẫu nhiên. Thay thế `(1, 100)` bằng phạm vi bạn mong muốn.

## Đi sâu hơn
Gói `random` của Haskell cung cấp một bộ sinh số ngẫu nhiên giả (PRNG), có nghĩa là các số được sinh ra không hoàn toàn ngẫu nhiên nhưng có thể xuất hiện ngẫu nhiên cho nhiều ứng dụng. Cốt lõi của khả năng sinh số ngẫu nhiên của Haskell nằm trong lớp kiểu `RandomGen`, mô phỏng các phương thức khác nhau để sinh số ngẫu nhiên, và lớp kiểu `Random`, bao gồm các kiểu có thể được sinh ra một cách ngẫu nhiên.

Lịch sử, cách tiếp cận của Haskell đối với việc sinh số ngẫu nhiên đã nhấn mạnh vào sự tinh khiết và khả năng tái sản xuất. Đây là lý do tại sao các hoạt động liên quan đến sự ngẫu nhiên được xử lý rõ ràng trong monad `IO` hoặc yêu cầu việc truyền và cập nhật trạng thái bộ sinh số một cách thủ công – để duy trì tính minh bạch tham chiếu.

Trong một số ứng dụng, như mật mã học, các số ngẫu nhiên giả do PRNG mặc định sinh ra có thể không đủ an toàn. Đối với những trường hợp sử dụng này, các lập trình viên Haskell thường chuyển sang các thư viện chuyên biệt hơn như `crypto-random`, được thiết kế để đáp ứng nhu cầu khắt khe của các ứng dụng mật mã học.

Hơn nữa, các thư viện alternative như `mwc-random` cung cấp hiệu suất tốt hơn và chất lượng số ngẫu nhiên tốt hơn cho các mô phỏng và ứng dụng khác, bằng cách thực hiện các thuật toán hiện đại như Mersenne Twister.

Khi chọn một phương pháp sinh số ngẫu nhiên trong Haskell, điều cần thiết là phải xem xét nhu cầu của ứng dụng về chất lượng ngẫu nhiên, hiệu suất, và an ninh để chọn công cụ hay thư viện phù hợp nhất.
