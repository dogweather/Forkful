---
title:                "处理CSV文件"
aliases:
- /zh/java/working-with-csv/
date:                  2024-02-03T19:20:19.384867-07:00
model:                 gpt-4-0125-preview
simple_title:         "处理CSV文件"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/java/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么及为什么？

处理 CSV 文件涉及从逗号分隔值（CSV）文件读取和向其写入数据，这是一种流行的数据交换格式，因为它简单且得到广泛支持。程序员操作 CSV 文件执行的任务，如数据导入/导出、数据分析，以及不同系统间的信息共享。

## 如何操作：

### 使用标准 Java 库读取 CSV 文件

Java 的标准库中没有内置对 CSV 的支持，但是您可以使用 `java.io` 类轻松读取 CSV 文件。

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadCSVExample {
    public static void main(String[] args) {
        String line;
        String csvFile = "data.csv"; // 指定 CSV 文件的路径
        try (BufferedReader br = new BufferedReader(new FileReader(csvFile))) {
            while ((line = br.readLine()) != null) {
                String[] values = line.split(","); // 假设逗号是分隔符
                // 处理数据
                for (String value : values) {
                    System.out.print(value + " ");
                }
                System.out.println();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 使用标准 Java 库写入 CSV 文件

要将数据写入 CSV 文件，您可以使用 `java.io` 类，如 `FileWriter` 和 `BufferedWriter`。

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class WriteCSVExample {
    public static void main(String[] args) {
        String[] data = {"John", "Doe", "30", "New York"};
        String csvFile = "output.csv"; // 指定输出 CSV 文件路径

        try (BufferedWriter bw = new BufferedWriter(new FileWriter(csvFile))) {
            StringBuilder sb = new StringBuilder();
            for (String value : data) {
                sb.append(value).append(","); // 假设逗号是分隔符
            }
            sb.deleteCharAt(sb.length() - 1); // 去除最后一个逗号
            bw.write(sb.toString());
            bw.newLine();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### 使用第三方库：Apache Commons CSV

Apache Commons CSV 是一个在 Java 中处理 CSV 文件的流行库。它大大简化了读取和写入 CSV 文件的操作。

向您的项目中添加依赖：

对于 Maven：

```xml
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-csv</artifactId>
    <version>1.9.0</version> <!-- 检查最新版本 -->
</dependency>
```

#### 读取 CSV 文件：

```java
import org.apache.commons.csv.CSVFormat;
import org.apache.commons.csv.CSVParser;
import org.apache.commons.csv.CSVRecord;

import java.io.Reader;
import java.io.FileReader;
import java.io.IOException;

public class ApacheReadCSVExample {
    public static void main(String[] args) {
        String csvFile = "data.csv";
        try (Reader reader = new FileReader(csvFile);
             CSVParser csvParser = new CSVParser(reader, CSVFormat.DEFAULT)) {
            for (CSVRecord csvRecord : csvParser) {
                // 通过列索引访问值
                String columnOne = csvRecord.get(0);
                String columnTwo = csvRecord.get(1);
                System.out.println(columnOne + " " + columnTwo);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

#### 写入 CSV 文件：

```java
import org.apache.commons.csv.CSVFormat;
import org.apache.commons.csv.CSVPrinter;

import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;

public class ApacheWriteCSVExample {
    public static void main(String[] args) {
        String[] headers = {"First Name", "Last Name", "Age", "City"};
        String[] data = {"John", "Doe", "30", "New York"};

        try (BufferedWriter writer = new BufferedWriter(new FileWriter("output.csv"));
             CSVPrinter csvPrinter = new CSVPrinter(writer, CSVFormat.DEFAULT.withHeader(headers))) {
            csvPrinter.printRecord((Object[]) data); // 这里需要将数据转换为 Object[] 类型
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

Apache Commons CSV 自动处理诸如字段内的引号和逗号之类的复杂情况，使其成为 Java 中操作 CSV 的强大选择。
