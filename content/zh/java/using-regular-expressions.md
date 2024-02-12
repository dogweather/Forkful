---
title:                "使用正则表达式"
aliases:
- zh/java/using-regular-expressions.md
date:                  2024-02-03T19:17:14.404067-07:00
model:                 gpt-4-0125-preview
simple_title:         "使用正则表达式"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/java/using-regular-expressions.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么和为什么？

Java中的正则表达式（regex）允许你定义特定模式来在代码中搜索、操作或验证字符串。程序员使用它们来执行像解析日志文件、验证用户输入或在文本中搜索特定模式的任务，从而以最小的努力实现复杂的字符串处理。

## 如何操作：

Java对regex的内置支持主要通过`java.util.regex`包中的`Pattern`和`Matcher`类。这里有一个简单的示例，用于查找并打印字符串中所有出现的单词，不区分大小写：

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexExample {
    public static void main(String[] args) {
        String text = "Regex is great for parsing. Parsing with regex is powerful.";
        String wordToFind = "parsing";
        
        Pattern pattern = Pattern.compile(wordToFind, Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher(text);
        
        while (matcher.find()) {
            System.out.println("在位置 " + matcher.start() + " 找到 '" + matcher.group() + "'");
        }
    }
}
```

输出：
```
在位置 16 找到 'parsing'
在位置 31 找到 'Parsing'
```

对于像字符串分割这样的任务，你可以使用`String`类的`split()`方法与regex一起使用：

```java
public class SplitExample {
    public static void main(String[] args) {
        String text = "Java,Python,Ruby,JavaScript";
        String[] languages = text.split(",");
        
        for (String language : languages) {
            System.out.println(language);
        }
    }
}
```

输出：
```
Java
Python
Ruby
JavaScript
```

在Java中使用regex时，可能会有一些情况下使用外部库可以简化复杂任务。一个用于Java中处理regex的流行第三方库是`Apache Commons Lang`。它提供了像`StringUtils`这样的实用程序，使某些regex任务更加简单。以下是如何使用它来计算子字符串的匹配次数：

```java
import org.apache.commons.lang3.StringUtils;

public class CommonsLangExample {
    public static void main(String[] args) {
        String text = "Regex makes text processing easier. Processing text with regex is efficient.";
        String substring = "processing";
        
        int count = StringUtils.countMatches(text, substring);
        System.out.println("'" + substring + "' 出现了 " + count + " 次。");
    }
}
```

要使用Apache Commons Lang，你需要将其包含在你的项目中。如果你使用Maven，将这个依赖项添加到你的`pom.xml`中：

```xml
<dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.12.0</version> <!-- 检查最新版本 -->
</dependency>
```

输出：
```
'processing' 出现了 2 次。
```
