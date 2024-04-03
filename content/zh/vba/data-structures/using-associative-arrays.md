---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:04:38.764807-07:00
description: "\u5173\u8054\u6570\u7EC4\u5728 Visual Basic for Applications (VBA) \u4E2D\
  \u901A\u5E38\u88AB\u79F0\u4E3A\u5B57\u5178\uFF0C\u5141\u8BB8\u7A0B\u5E8F\u5458\u521B\
  \u5EFA\u952E\u503C\u5BF9\u96C6\u5408\u3002\u8FD9\u4E00\u7279\u6027\u5BF9\u4E8E\u9AD8\
  \u6548\u7684\u6570\u636E\u5B58\u50A8\u548C\u68C0\u7D22\u81F3\u5173\u91CD\u8981\uFF0C\
  \u63D0\u4F9B\u4E86\u4E00\u79CD\u6BD4\u4F20\u7EDF\u6570\u7EC4\u7D22\u5F15\u66F4\u7075\
  \u6D3B\u76F4\u89C2\u7684\u6570\u636E\u7BA1\u7406\u65B9\u5F0F\u3002"
lastmod: '2024-03-13T22:44:47.563500-06:00'
model: gpt-4-0125-preview
summary: "\u5173\u8054\u6570\u7EC4\u5728 Visual Basic for Applications (VBA) \u4E2D\
  \u901A\u5E38\u88AB\u79F0\u4E3A\u5B57\u5178\uFF0C\u5141\u8BB8\u7A0B\u5E8F\u5458\u521B\
  \u5EFA\u952E\u503C\u5BF9\u96C6\u5408\u3002\u8FD9\u4E00\u7279\u6027\u5BF9\u4E8E\u9AD8\
  \u6548\u7684\u6570\u636E\u5B58\u50A8\u548C\u68C0\u7D22\u81F3\u5173\u91CD\u8981\uFF0C\
  \u63D0\u4F9B\u4E86\u4E00\u79CD\u6BD4\u4F20\u7EDF\u6570\u7EC4\u7D22\u5F15\u66F4\u7075\
  \u6D3B\u76F4\u89C2\u7684\u6570\u636E\u7BA1\u7406\u65B9\u5F0F\u3002."
title: "\u4F7F\u7528\u5173\u8054\u6570\u7EC4"
weight: 15
---

## 如何操作：
在 VBA 中，`Dictionary` 对象提供了类似于关联数组的功能。你必须首先添加对 Microsoft Scripting Runtime 的引用才能使用它：

1. 在 VBA 编辑器中，转至 工具 > 引用...
2. 勾选 “Microsoft Scripting Runtime” 并点击确定。

下面是如何声明、填充和访问 `Dictionary` 中的项目：

```vb
Dim sampleDictionary As Dictionary
Set sampleDictionary = New Dictionary

' 添加项目
sampleDictionary.Add Key:="Name", Item:="John Doe"
sampleDictionary.Add Key:="Age", Item:=29
sampleDictionary.Add Key:="Occupation", Item:="Engineer"

' 访问项目
Debug.Print sampleDictionary.Item("Name")  ' 输出: John Doe
Debug.Print sampleDictionary.Item("Age")   ' 输出: 29

' 检查键是否存在
If sampleDictionary.Exists("Occupation") Then
    Debug.Print "Occupation 键存在"
End If

' 移除项目
sampleDictionary.Remove("Occupation")

' 遍历字典
For Each Key In sampleDictionary.Keys
    Debug.Print Key & ": " & sampleDictionary.Item(Key)
Next Key
```

## 深入了解
`Dictionary` 对象在底层接口上与 Windows 脚本宿主的组件对接。因此，它是一个后期绑定的 COM 对象，这曾是过去扩展 VBA 功能的常见方式。其在 VBA 中的使用可以显著增强语言处理复杂数据集的能力，而不强制执行传统数组或 Excel 范围中看到的刚性结构。

需要注意的一个限制是访问 `Dictionary` 需要设置对 Microsoft Scripting Runtime 的引用，这可能会使分发你的 VBA 项目复杂化。VBA 内部存在替代品如 Collections，但缺少一些 `Dictionary` 的关键特性，例如在不触发错误的情况下轻松检查键是否存在的能力。

在更现代的编程环境中，像 Python 这样的语言提供了对关联数组（在 Python 中也称为字典）的内置支持，无需添加外部引用。这种内置支持简化了过程，并提供了更多高级功能。然而，在 VBA 的限制内，以及针对自动化 Microsoft Office 套件任务的特定应用程序中，使用 `Dictionary` 对象仍然是一种强大且相关的方法，用于类似关联数组的数据结构。
