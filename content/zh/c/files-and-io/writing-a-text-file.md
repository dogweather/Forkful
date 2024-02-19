---
aliases:
- /zh/c/writing-a-text-file/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:14:37.190108-07:00
description: "\u5728C\u8BED\u8A00\u4E2D\u5199\u5165\u6587\u672C\u6587\u4EF6\u6D89\u53CA\
  \u5230\u5728\u5199\u6A21\u5F0F\u4E0B\u521B\u5EFA\u6216\u6253\u5F00\u6587\u4EF6\uFF0C\
  \u7136\u540E\u4F7F\u7528C\u7684\u6587\u4EF6I/O\u51FD\u6570\u5C06\u6587\u672C\u6570\
  \u636E\u4FDD\u5B58\u81F3\u5176\u4E2D\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\
  \u4E3A\u4E86\u6301\u4E45\u5316\u6570\u636E\uFF0C\u5982\u65E5\u5FD7\u4E8B\u4EF6\u3001\
  \u914D\u7F6E\u8BBE\u7F6E\u6216\u7528\u6237\u751F\u6210\u7684\u5185\u5BB9\uFF0C\u4F7F\
  \u5F97\u5E94\u7528\u80FD\u591F\u5728\u4F1A\u8BDD\u4E4B\u95F4\u4FDD\u6301\u72B6\u6001\
  \u3001\u504F\u597D\u8BBE\u7F6E\u6216\u7528\u6237\u8FDB\u5EA6\u3002"
lastmod: 2024-02-18 23:08:59.577247
model: gpt-4-0125-preview
summary: "\u5728C\u8BED\u8A00\u4E2D\u5199\u5165\u6587\u672C\u6587\u4EF6\u6D89\u53CA\
  \u5230\u5728\u5199\u6A21\u5F0F\u4E0B\u521B\u5EFA\u6216\u6253\u5F00\u6587\u4EF6\uFF0C\
  \u7136\u540E\u4F7F\u7528C\u7684\u6587\u4EF6I/O\u51FD\u6570\u5C06\u6587\u672C\u6570\
  \u636E\u4FDD\u5B58\u81F3\u5176\u4E2D\u3002\u7A0B\u5E8F\u5458\u8FD9\u6837\u505A\u662F\
  \u4E3A\u4E86\u6301\u4E45\u5316\u6570\u636E\uFF0C\u5982\u65E5\u5FD7\u4E8B\u4EF6\u3001\
  \u914D\u7F6E\u8BBE\u7F6E\u6216\u7528\u6237\u751F\u6210\u7684\u5185\u5BB9\uFF0C\u4F7F\
  \u5F97\u5E94\u7528\u80FD\u591F\u5728\u4F1A\u8BDD\u4E4B\u95F4\u4FDD\u6301\u72B6\u6001\
  \u3001\u504F\u597D\u8BBE\u7F6E\u6216\u7528\u6237\u8FDB\u5EA6\u3002"
title: "\u7F16\u5199\u6587\u672C\u6587\u4EF6"
---

{{< edit_this_page >}}

## 什么以及为什么？

在C语言中写入文本文件涉及到在写模式下创建或打开文件，然后使用C的文件I/O函数将文本数据保存至其中。程序员这样做是为了持久化数据，如日志事件、配置设置或用户生成的内容，使得应用能够在会话之间保持状态、偏好设置或用户进度。

## 如何：

要在C语言中向文件写入文本，你主要需要熟悉`fopen()`、`fprintf()`、`fputs()`和`fclose()`函数。下面是一个简单的例子，演示了创建文件并写入的过程：

```c
#include <stdio.h>

int main() {
    FILE *filePointer;
    // 以写模式打开文件。如果文件不存在，则会创建。
    filePointer = fopen("example.txt", "w");
    
    if(filePointer == NULL) {
        printf("文件无法打开\n");
        return 1; // 如果文件指针返回NULL，则退出程序。
    }
    
    // 写入文件
    fprintf(filePointer, "这是一个写入文件的示例。\n");
    fputs("这里是另外一行文本。\n", filePointer);
    
    // 关闭文件以保存更改
    fclose(filePointer);
    
    printf("文件成功写入\n");
    return 0;
}
```

成功执行后的示例输出：
```
文件成功写入
```

运行此程序后，你会在同一目录下找到一个名为`example.txt`的文件，其中包含了你通过`fprintf()`和`fputs()`写入的文本。

## 深入探讨

文件和文件系统的概念对计算机系统至关重要，其管理是操作系统的一个关键方面。在C语言中，文件处理是使用一系列标准I/O库函数来执行的，这套函数的哲学是把文件视为字节流。这种抽象提供了一个简单而有效的读写文件方法，虽然与Python或Ruby等更高级语言提供的现代方法相比，它可能看起来更低级。

从历史上看，C语言中的这些文件I/O操作为许多编程语言中的文件操纵奠定了基础，提供了与操作系统的文件管理系统紧密相连的接口。这不仅提供了对文件属性和I/O操作的细粒度控制，还为不小心的程序员设下了陷阱，如需要手动管理资源（即，总是关闭文件）和缓冲问题。

虽然C语言中的基本文件I/O函数功能强大，足以完成许多任务，但它们缺乏现代语言提供的便利性和高级抽象。如Python通过使用`with`语句自动化内存管理和文件关闭，大大减少了样板代码和资源泄漏的风险。对于需要复杂文件操作或高级抽象（如文件锁、异步I/O或监视文件系统事件）的应用，最好是考虑使用提供这些功能的库，或选择天生支持这些构造的语言。

尽管如此，理解C语言中的文件I/O是非常宝贵的，它提供了对高级语言如何实现这些功能的深入见解，并提供了编写高效、底层代码的工具，当性能和控制至关重要时。
