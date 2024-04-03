---
date: 2024-01-26 03:37:40.826127-07:00
description: "\u91CD\u6784\u662F\u5728\u4E0D\u6539\u53D8\u5176\u5916\u90E8\u884C\u4E3A\
  \u7684\u60C5\u51B5\u4E0B\u91CD\u65B0\u7ED3\u6784\u73B0\u6709\u8BA1\u7B97\u673A\u4EE3\
  \u7801\u7684\u8FC7\u7A0B\uFF0C\u76EE\u7684\u662F\u6539\u5584\u8F6F\u4EF6\u7684\u975E\
  \u529F\u80FD\u5C5E\u6027\u3002\u7A0B\u5E8F\u5458\u91CD\u6784\u4EE3\u7801\u662F\u4E3A\
  \u4E86\u8BA9\u4EE3\u7801\u66F4\u6E05\u6670\u3001\u66F4\u9AD8\u6548\u3001\u66F4\u6613\
  \u4E8E\u7406\u89E3\uFF0C\u4ECE\u800C\u4FBF\u4E8E\u66F4\u5BB9\u6613\u5730\u7EF4\u62A4\
  \u548C\u672A\u6765\u7684\u589E\u5F3A\u3002"
lastmod: '2024-03-13T22:44:48.023301-06:00'
model: gpt-4-0125-preview
summary: "\u91CD\u6784\u662F\u5728\u4E0D\u6539\u53D8\u5176\u5916\u90E8\u884C\u4E3A\
  \u7684\u60C5\u51B5\u4E0B\u91CD\u65B0\u7ED3\u6784\u73B0\u6709\u8BA1\u7B97\u673A\u4EE3\
  \u7801\u7684\u8FC7\u7A0B\uFF0C\u76EE\u7684\u662F\u6539\u5584\u8F6F\u4EF6\u7684\u975E\
  \u529F\u80FD\u5C5E\u6027\u3002\u7A0B\u5E8F\u5458\u91CD\u6784\u4EE3\u7801\u662F\u4E3A\
  \u4E86\u8BA9\u4EE3\u7801\u66F4\u6E05\u6670\u3001\u66F4\u9AD8\u6548\u3001\u66F4\u6613\
  \u4E8E\u7406\u89E3\uFF0C\u4ECE\u800C\u4FBF\u4E8E\u66F4\u5BB9\u6613\u5730\u7EF4\u62A4\
  \u548C\u672A\u6765\u7684\u589E\u5F3A\u3002."
title: "\u91CD\u6784"
weight: 19
---

## 如何操作：
PowerShell内置的并没有专门的重构工具，但你仍然可以清理你的代码，以提高可读性和性能。考虑一个做得太多的函数，以及我们如何为了清晰而重构它：

```PowerShell
function Get-InventoryData {
    # 原始函数结合了数据检索和格式化
    $data = Get-Content -Path 'C:\inventory-list.txt'
    $inventoryData = $data | ForEach-Object {
        $fields = $_ -split ','
        [PSCustomObject]@{
            ItemID = $fields[0]
            Name   = $fields[1]
            Count  = $fields[2]
            Price  = $fields[3]
        }
    }
    $inventoryData | Format-Table -AutoSize
}

# 重构为独立的函数
function Import-InventoryData {
    param($Path)
    Get-Content -Path $Path | ForEach-Object {
        $fields = $_ -split ','
        [PSCustomObject]@{
            ItemID = $fields[0]
            Name   = $fields[1]
            Count  = $fields[2]
            Price  = $fields[3]
        }
    }
}

function Format-InventoryData {
    param($Data)
    $Data | Format-Table -AutoSize
}

# 使用案例
$inventory = Import-InventoryData -Path 'C:\inventory-list.txt'
Format-InventoryData -Data $inventory
```

样本输出：

```
ItemID Name            Count Price
------ ----            ----- -----
1001   Widget Type A   50    9.99
1002   Gadget Type B   20    14.99
```

## 深入探索
编程中的重构根源可以追溯到软件开发的最初日子，尽管到了1990年代，重构作为一种实践才被正式化。马丁·福勒的《重构：改善既有代码的设计》是该主题上的开创性著作之一，强调了重构在实现清晰代码中的重要性。

尽管PowerShell没有像其他语言的一些集成开发环境（IDE）那样的具体重构工具（比如Eclipse或Visual Studio），但你仍然可以手动实践良好的重构原则。需要记住的关键一点是，重构不仅仅是为了改变代码而改变代码，而是做出有意的、保持行为的修改，以增强代码的结构和设计。

PowerShell手动重构的替代方式包括使用支持该语言的IDE，如带有PowerShell扩展的Visual Studio Code，它提供了代码格式化和基本重构能力等特性。对于更重要的重构，你可能考虑利用Pester测试来确保更改不会改变功能。

此外，重构的实现可以涉及更多系统性的变化，如模块化，其中代码被分割成可重用的模块或函数，改进了DRY（不要自己重复）原则的遵守。其他常见的重构技术包括为了清晰而重命名、移除重复代码，以及减少条件逻辑的复杂性。

## 另请参见
要深入了解，这里有一些资源：

- 马丁·福勒的重构书：[《重构：改善既有代码的设计》](https://martinfowler.com/books/refactoring.html)
- 使用Pester测试重构后的代码：[Pester测试框架](https://pester.dev/)
- PowerShell最佳实践：[PowerShell最佳实践和风格指南](https://poshcode.gitbooks.io/powershell-practice-and-style/)
