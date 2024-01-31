---
title:                "使用关联数组"
date:                  2024-01-30T19:12:12.131204-07:00
model:                 gpt-4-0125-preview
simple_title:         "使用关联数组"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/javascript/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## 什么 & 为什么？

关联数组，在JavaScript中更准确地称为对象，让你能够将键映射到值。当你需要一个元素集合，并希望通过特定名称（键）而不是数字索引来访问它们时，这非常方便，使你的代码更易读和灵活。

## 如何：

在JavaScript中创建和使用关联数组（对象）非常直接。你用花括号`{}`定义一个对象，在其中，你可以定义一组键值对。键总是字符串，而值可以是任何东西：字符串，数字，数组，甚至其他对象。

```javascript
// 创建关联数组
let userInfo = {
  name: "Alex",
  age: 30,
  email: "alex@example.com"
};

// 访问元素
console.log(userInfo.name); // 输出：Alex
console.log(userInfo["email"]); // 输出：alex@example.com

// 添加新元素
userInfo.job = "Developer";
userInfo["country"] = "Canada";

console.log(userInfo);
/* 输出：
{
  name: "Alex",
  age: 30,
  email: "alex@example.com",
  job: "Developer",
  country: "Canada"
}
*/

// 删除元素
delete userInfo.age;
console.log(userInfo);
/* 输出：
{
  name: "Alex",
  email: "alex@example.com",
  job: "Developer",
  country: "Canada"
}
*/
```

如你所见，访问、添加或删除关联数组中的元素非常直接和直观。

## 深入探讨

在JavaScript世界中，尽管我们经常听到“关联数组”这个术语，但从技术上讲，这是一个不太恰当的称呼，因为JavaScript与其他语言（例如，PHP）不同，没有真正的关联数组。JavaScript拥有的是对象，这类似于关联数组的服务目的，但构建得更加强大和灵活。

从历史上看，编程语言中的数组被设计为容纳一个由数值索引访问的项目集合。然而，随着软件开发的演进，对更灵活数据结构的需求浮现了。关联数组，或在其他语言中称为字典，是其中一个回应，允许通过任意键访问元素。

JavaScript使用对象作为键值存储的做法提供了一种功能性的融合。它允许属性（键）被添加、删除，并通过名称查找。JSON（JavaScript Object Notation）证明了这种结构的实用性，成为网络上数据交换的事实标准。

尽管对象在大多数情况下都能满足关联数组的需要，但在键顺序或迭代很重要的情况下，ES6中引入的`Map`对象提供了更好的选择。`Map`保留键顺序，接受更广泛的数据类型作为键，并包含有助于迭代和大小检索的有用方法。尽管有这些优势，传统的对象语法因其简单性和在许多常见场景下的易用性而保持流行。
