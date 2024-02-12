---
title:                "处理错误"
aliases:
- zh/vba/handling-errors.md
date:                  2024-02-01T21:55:05.586122-07:00
model:                 gpt-4-0125-preview
simple_title:         "处理错误"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/vba/handling-errors.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么与为什么？

Visual Basic for Applications (VBA) 中的错误处理指的是预期、检测和解决编程、应用程序或通信错误的过程。实现强大的错误处理对于保持应用程序的完整性和通过优雅地管理意外问题改善用户体验至关重要，无需导致突然崩溃或数据丢失。

## 如何操作：

在 VBA 中，错误处理通常使用 `On Error` 语句来实现，该语句指示 VBA 在发生错误时如何继续。最常见的错误处理策略包括 `On Error GoTo` 标签、`On Error Resume Next` 和 `On Error GoTo 0`。

**示例 1：使用 `On Error GoTo`**

此方法允许您在遇到错误后立即将程序指向代码的特定部分，该部分被标记为。

```vb
Sub ErrorHandlerExample()
    On Error GoTo ErrHandler
    Dim intDivision As Integer

    intDivision = 5 / 0 ' 这将导致除以零错误

    Exit Sub
ErrHandler:
    MsgBox "发生错误：" & Err.Description, vbCritical, "错误！"
    Resume Next
End Sub
```

在此示例中，任何运行时错误将触发跳转到 `ErrHandler`，显示错误消息，然后继续执行错误后的下一行。

**示例 2：使用 `On Error Resume Next`**

该策略指示 VBA 即使发生错误也继续执行下一行代码，这对于预期无害的错误或当您计划稍后在执行中处理错误时非常有用。

```vb
Sub ResumeNextExample()
    On Error Resume Next
    Dim intDivision As Integer
    intDivision = 5 / 0 ' 这不会导致程序停止；错误被忽略
    
    ' 检查是否发生错误
    If Err.Number <> 0 Then
        MsgBox "发生错误：" & Err.Description, vbExclamation, "已处理错误"
        ' 重置错误
        Err.Clear
    End If
End Sub
```

在这种情况下，程序在出错时不会中断；它检查是否发生了错误，如果发生了则处理它，然后清除错误。

## 深入探讨

从历史上看，编程语言中的错误处理已从简单的 goto 语句发展为更复杂的机制，如 Java 和 C# 等语言中的异常。VBA 的错误处理虽然不像现代异常处理那样强大或灵活，但在该语言在 Microsoft Office 环境中自动化任务的上下文中发挥其作用。

VBA 错误处理的主要限制在于其有些繁琐和手动的方法，需要仔细放置错误处理代码和清晰理解执行流程。现代编程语言通常提供更优雅的解决方案，例如 try-catch 块，无需手动检查或代码执行中的跳转即可自动处理错误处理代码的流程。

尽管有这些限制，VBA 的错误处理机制适用于大多数自动化任务，当正确使用时，可以显著降低未处理错误对用户造成问题的可能性。此外，理解 VBA 的错误处理可以提供对旧编程范例和软件开发中错误处理策略进化的洞察。
