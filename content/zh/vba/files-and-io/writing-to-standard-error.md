---
title:                "写入标准错误"
aliases:
- /zh/vba/writing-to-standard-error/
date:                  2024-02-01T22:09:08.319115-07:00
model:                 gpt-4-0125-preview
simple_title:         "写入标准错误"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/vba/writing-to-standard-error.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么？

在Visual Basic for Applications (VBA) 中写入标准错误涉及将错误消息或诊断信息从标准输出中分离出来，通常输出到控制台或日志文件。程序员这样做是为了将常规程序输出与错误消息分开，使得程序调试或提示用户出现问题时不会混淆主要输出。

## 如何操作：

在VBA中，由于没有直接的内置函数专门用于写入标准错误，与一些其他编程语言不同，一个常见的解决方法是使用`Debug.Print`进行开发时的错误输出，或为生产应用创建一个模拟此行为的自定义日志功能。以下是一个实现和使用此类功能的示例：

```vb
Sub WriteToErrorLog(msg As String)
    ' 自定义功能以模拟写入标准错误
    ' 在实际部署中，这可能写入到一个单独的日志文件或一个专用的调试窗口
    Open "ErrorLog.txt" For Append As #1 ' 将"ErrorLog.txt"更改为所需的日志文件路径
    Print #1, "ERROR: " & msg
    Close #1
    Debug.Print "ERROR: " & msg ' 同时输出到IDE中的立即窗口以便开发人员的调试
End Sub

Sub Demonstration()
    ' WriteToErrorLog功能的示例用法
    WriteToErrorLog "在处理您的请求时发生了错误。"
End Sub
```

"ErrorLog.txt"中的示例输出可能如下所示：
```
ERROR: 在处理您的请求时发生了错误。
```

以及在VBA IDE中的立即窗口中：
```
ERROR: 在处理您的请求时发生了错误。
```

## 深入探讨

由于Visual Basic for Applications与主机应用程序（如Excel、Word或Access）的集成性质深入，因此本身并不包括专门用于写入标准错误的专用机制，这些主机应用程序传统上依赖于图形用户界面而非控制台输出。这与通常在C或Python等语言中开发的基于控制台的应用程序形成了显著差异，在那里标准输出和标准错误流是基本概念。

从历史上看，VBA的重点始终更多地在与其主机应用程序的文档模型交互上，而不是传统的应用程序日志记录机制上。因此，开发人员常常采用实现自定义日志解决方案，如示例中所示，或利用Windows API调用来满足更高级的错误处理和日志记录需求。

虽然展示的方法提供了一种解决方案，但对于寻求更健壮的日志与错误处理的开发人员，可能会探索与外部系统或库集成，这些系统或库能够实现更复杂的日志记录。在现代开发中，尤其是关注调试和维护的情况下，清晰、有上下文且分开记录标准输出与错误输出的重要性不容忽视，这促使许多人寻求超越VBA本身能力的解决方案。
