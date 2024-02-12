---
title:                "处理XML"
aliases:
- /zh/powershell/working-with-xml/
date:                  2024-01-26T04:34:19.703762-07:00
model:                 gpt-4-0125-preview
simple_title:         "处理XML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/powershell/working-with-xml.md"
---

{{< edit_this_page >}}

## 什么和为什么？
使用 XML 涉及到操作和访问以可扩展标记语言（eXtensible Markup Language）结构化的数据。程序员使用 XML 是为了实现与其他系统的互操作性，或是为了读写配置文件、数据源和网络服务中常见的其他结构化文档。

## 如何操作：
```PowerShell
# 将一个 XML 文件加载到变量中
[xml]$xmlContent = Get-Content 'path\to\your\file.xml'

# 访问 XML 节点
$books = $xmlContent.catalog.book
foreach ($book in $books) {
  Write-Output "标题: $($book.title)"
}

# 创建一个新的 XML 元素
$newBook = $xmlContent.CreateElement("book")
$newBook.SetAttribute("id", "bk999")
$xmlContent.DocumentElement.AppendChild($newBook)

# 将 XML 保存回文件
$xmlContent.Save('path\to\your\updated\file.xml')
```
示例输出：
```
标题: 编程 PowerShell
标题: XML 基础
```

## 深入了解
XML 或可扩展标记语言，自 90 年代末起就已经存在，它仍然是一种被广泛使用的结构化数据格式。与传统的解析方法相比，PowerShell 简化了处理 XML 的过程；它直接将 XML 转换为对象，让你通过熟悉的点表示法与元素交互。

XML 的替代品包括 JSON、YAML 或自定义数据格式。例如，JSON 因其轻量级性质以及与网络技术的易用性而获得了普及。然而，XML 的扩展特性，如命名空间、模式和 XSLT 处理，通常使其更适合复杂文档或行业标准。

PowerShell 使用 .NET Framework 的 XML 功能来处理 XML。这意味着它不仅仅是关于简单的读写操作；你还可以使用 XML 模式进行验证，使用 XPath 进行查询，以及通过 PowerShell 进行 XSLT 转换。

## 另请参阅
- [W3Schools XML 教程](https://www.w3schools.com/xml/)
- [XML 与 JSON](https://www.json.org/json-en.html)
