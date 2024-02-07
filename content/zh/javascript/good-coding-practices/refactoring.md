---
title:                "重构代码"
date:                  2024-01-26T01:43:00.486571-07:00
model:                 gpt-4-0125-preview
simple_title:         "重构代码"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/javascript/refactoring.md"
---

{{< edit_this_page >}}

## 什么与为什么？
重构是指在不改变现有计算机代码外部行为的前提下，对其进行结构调整的过程。程序员之所以进行重构，是为了改善软件的非功能属性，使代码更加清晰、高效，进而简化维护工作，并使得未来添加新功能变得更加容易。

## 如何操作：

让我们看一个简单的例子，通过重构让你的代码更加简洁、可读。这里，我们重构一个计算数字数组之和的函数。

重构前：
```javascript
function calculateSum(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
}

console.log(calculateSum([1, 2, 3, 4])); // 输出：10
```

重构后：
```javascript
function calculateSum(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}

console.log(calculateSum([1, 2, 3, 4])); // 输出：10
```

看到了吗，`reduce` 方法如何在保持功能完整的同时减少了函数的大小？这就是重构的力量。

## 深入探究

直到1999年Martin Fowler出版了《重构：改善既有代码的设计》一书，重构才作为一种正式的实践出现。这本书和敏捷软件开发的兴起一起，帮助将重构推向了主流。

将重构描述为软件开发的一个方面，就像解释为什么你要整理一个工作室一样：你这么做是为了下次你需要修理某些东西（在这种情况下是代码）时，能够花更少的时间处理混乱，更多地关注实际问题。

当我们讨论重构的替代方案时，我们进入了有关软件维护策略的更广泛讨论。例如，人们可以选择全面重写，但那通常更昂贵且风险更高。渐进式地重构，你就能在不因突然大修而使船沉的情况下，持续获益。

重构得益于集成开发环境（IDEs）和如JSHint、ESLint及Prettier等JavaScript生态系统中的工具的发展，这些工具自动检查代码质量并突出显示重构的机会。

这一切都与干净、表达力强、易于维护的代码有关。复杂算法、数据结构优化，甚至是像从过程式转换到函数式编程风格这样的架构变更可能是重构过程的一部分。

重构必须谨慎进行；确保你的更改没有意外改变软件的行为，这至关重要——这也是为什么测试驱动开发（TDD）与重构非常契合的另一个原因，因为它默认提供了这样的安全网。

## 另请参阅

- Martin Fowler的重构书：[《重构 - 改善既有代码的设计》](https://martinfowler.com/books/refactoring.html)
- JavaScript测试框架（确保重构不破坏功能性）：
  - Jest: [Jest - 令人愉快的JavaScript测试](https://jestjs.io/)
  - Mocha: [Mocha - 有趣、简单、灵活的JavaScript测试框架](https://mochajs.org/)

- 支持代码质量和重构的工具：
  - ESLint: [ESLint - 可插拔的JavaScript检查器](https://eslint.org/)
  - Prettier: [Prettier - 固执的代码格式化器](https://prettier.io/)
