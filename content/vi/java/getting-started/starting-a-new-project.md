---
aliases:
- /vi/java/starting-a-new-project/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:09:10.403282-07:00
description: "B\u1EAFt \u0111\u1EA7u m\u1ED9t d\u1EF1 \xE1n Java m\u1EDBi gi\u1ED1\
  ng nh\u01B0 vi\u1EC7c thi\u1EBFt l\u1EADp m\u1ED9t b\u1EE9c tranh m\u1EDBi cho ki\u1EC7\
  t t\xE1c c\u1EE7a b\u1EA1n. L\u1EADp tr\xECnh vi\xEAn kh\u1EDFi \u0111\u1EA7u c\xE1\
  c d\u1EF1 \xE1n m\u1EDBi \u0111\u1EC3 bi\u1EBFn \xFD t\u01B0\u1EDFng th\xE0nh\u2026"
lastmod: 2024-02-18 23:08:50.557892
model: gpt-4-0125-preview
summary: "B\u1EAFt \u0111\u1EA7u m\u1ED9t d\u1EF1 \xE1n Java m\u1EDBi gi\u1ED1ng nh\u01B0\
  \ vi\u1EC7c thi\u1EBFt l\u1EADp m\u1ED9t b\u1EE9c tranh m\u1EDBi cho ki\u1EC7t t\xE1\
  c c\u1EE7a b\u1EA1n. L\u1EADp tr\xECnh vi\xEAn kh\u1EDFi \u0111\u1EA7u c\xE1c d\u1EF1\
  \ \xE1n m\u1EDBi \u0111\u1EC3 bi\u1EBFn \xFD t\u01B0\u1EDFng th\xE0nh\u2026"
title: "B\u1EAFt \u0111\u1EA7u m\u1ED9t d\u1EF1 \xE1n m\u1EDBi"
---

{{< edit_this_page >}}

## Gì và Tại sao?

Bắt đầu một dự án Java mới giống như việc thiết lập một bức tranh mới cho kiệt tác của bạn. Lập trình viên khởi đầu các dự án mới để biến ý tưởng thành phần mềm chức năng, và mỗi lần bắt đầu mới là một bước đi hướng tới đổi mới hoặc giải quyết một vấn đề.

## Cách thực hiện:

Hãy bắt đầu thôi. Chúng tôi sẽ tạo một dự án Java đơn giản sử dụng dòng lệnh và biên dịch và chạy chương trình "Hello, World!" cổ điển.

Đầu tiên, hãy tạo một thư mục cho dự án của bạn và di chuyển vào nó:

```bash
mkdir MyJavaProject
cd MyJavaProject
```

Bây giờ, hãy tạo tệp Java của bạn:

```bash
echo 'public class HelloWorld { public static void main(String[] args) { System.out.println("Hello, World!"); }}' > HelloWorld.java
```

Đã đến lúc biên dịch:

```bash
javac HelloWorld.java
```

Chạy kiệt tác của bạn:

```bash
java HelloWorld
```

Xin chúc mừng! Console sẽ hiển thị:

```java
Hello, World!
```

## Sâu hơn:

Ngày xửa ngày xưa, các dự án Java được quản lý một cách thủ công, một chút giống như việc tung hứng tệp trong một rạp xiếc. Ngày nay, chúng ta có những công cụ như Maven và Gradle để tự động hóa những công việc tẻ nhạt.

Maven, ví dụ, đã định rõ một cấu trúc dự án tiêu chuẩn mà phần lớn các nhà phát triển Java ngày nay đều quen thuộc. Nó cũng xử lý các phụ thuộc để bạn không phải tự tải xuống jar và chiến đấu với những cơn ác mộng về classpath.

Gradle đã xuất hiện sau đó, cung cấp nhiều tính linh hoạt hơn và sử dụng một DSL (Ngôn Ngữ Đặc Thù Lĩnh Vực) dựa trên Groovy cho việc viết kịch bản. Nó giống như Maven, nhưng với nhiều tự do hơn cho các kịch bản tùy chỉnh mà không cần thêm plugin.

Có phương án thay thế? Chắc chắn, có Ant với Ivy, nhưng nó hơi cổ điển, giống như việc nghe nhạc trên băng cassette. Bạn phải yêu thích sự hoài cổ, nhưng nó có thể không phải cho mọi người trong kỷ nguyên của các dịch vụ phát trực tuyến này.

Khi bạn bắt đầu một dự án Java mới, hãy suy nghĩ về mức độ lớn và phức tạp của nó. Đối với việc học hoặc các dự án nhỏ, việc quản lý thủ công hoạt động tốt. Nhưng nếu bạn đang lên kế hoạch xây dựng điều gì đó quan trọng hoặc làm việc trong một nhóm, công cụ xây dựng chính là cách đi.

## Xem thêm:

Để có được lợi thế khi sử dụng công cụ xây dựng, hãy xem xét những điều sau:

- [Hướng dẫn Bắt Đầu Với Maven](https://maven.apache.org/guides/getting-started/index.html)
- [Xây Dựng Dự Án Java Với Gradle](https://spring.io/guides/gs/gradle/)
- [Giới thiệu về Ant](https://ant.apache.org/manual/index.html)

Và cho những ai muốn khám phá sâu hơn về các tính năng mới của JDK, [Tài liệu Oracle về Java Platform, Standard Edition](https://docs.oracle.com/en/java/javase/index.html) là một kho báu.
