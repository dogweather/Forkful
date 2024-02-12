---
title:                "使用关联数组"
aliases:
- zh/fish-shell/using-associative-arrays.md
date:                  2024-01-30T19:11:05.473628-07:00
model:                 gpt-4-0125-preview
simple_title:         "使用关联数组"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/fish-shell/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么和为什么？

关联数组或哈希映射允许您以键值对的形式存储数据，这使得通过键组织和检索信息变得更加容易。当您需要一种比列表更有结构的方式来处理数据时，它们非常方便，尤其是在配置以及处理一系列属性时。

## 如何操作：

Fish本身并不像Bash 4+那样原生支持关联数组，但您可以使用列表和字符串操作的组合来实现类似的功能。以下是模拟它们的方式：

首先，分别设置“关联数组”元素：

```Fish Shell
set food_color_apple "red"
set food_color_banana "yellow"
```

要访问一个元素，直接引用它即可：

```Fish Shell
echo $food_color_apple
# 输出：red
```

如果您需要遍历它们，使用for循环并考虑命名约定：

```Fish Shell
for food in apple banana
    echo $food_color_$food
end
# 输出：
# red
# yellow
```

对于那些缺少Bash的`${!array[@]}`来获取所有键的人，您可以在一个单独的列表中存储键：

```Fish Shell
set food_keys apple banana

for key in $food_keys
    echo $key '是' $food_color_$key
end
# 输出：
# apple 是 red
# banana 是 yellow
```

## 深入探讨

真正的关联数组，如其他脚本语言中的，尚未成为Fish方法的一部分。所展示的解决方法利用了Fish的字符串操作和列表功能来创建一个伪关联数组结构。虽然它有效，但并不如内置的关联数组支持那样干净或防错。其他shell，如Bash和Zsh，提供了内置的关联数组功能，这导致更直接、可读的代码。然而，Fish的设计理念旨在追求简洁性和用户友好性，可能以牺牲这类功能为代价。这种解决方法满足了大多数需求，但请关注Fish Shell的发展——其开发人员根据社区反馈积极改进和增加功能。
