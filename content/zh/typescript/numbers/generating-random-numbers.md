---
title:                "生成随机数"
aliases:
- /zh/typescript/generating-random-numbers/
date:                  2024-01-27T20:35:44.444823-07:00
model:                 gpt-4-0125-preview
simple_title:         "生成随机数"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/typescript/generating-random-numbers.md"
---

{{< edit_this_page >}}

## 什么 & 为什么？

在 TypeScript 中生成随机数是指在指定范围内创建不可预测的数值。程序员利用这些随机数字进行各种目的，如生成唯一标识符、模拟数据进行测试，或为游戏和模拟增加不可预测性。

## 如何操作：

在 TypeScript 中，你可以使用全局的 `Math` 对象来生成随机数。下面是一些实际示例，展示如何根据不同的需求产生随机数。

### 生成基本随机数

要生成一个介于 0（包括）和 1（不包括）之间的基本随机小数，你使用 `Math.random()`。这不需要任何额外的操作：

```TypeScript
const randomNumber = Math.random();
console.log(randomNumber);
```

这可能会输出像 `0.8995452185604771` 这样的值。

### 生成两个值之间的随机整数

当你需要在两个特定值之间生成一个整数时，你会结合使用 `Math.random()` 和一些算术操作：

```TypeScript
function getRandomInt(min: number, max: number): number {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}

const randomInt = getRandomInt(1, 10);
console.log(randomInt);
```

这可能输出一个介于 1 和 10 之间的整数值，例如 `7`。

### 生成唯一标识符

可以将随机数与其他方法结合使用以创建唯一标识符，例如，一个简单的 UUID 生成代码片段：

```TypeScript
function generateUUID(): string {
    return 'xxxxyxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, (c) => {
        const r = Math.random() * 16 | 0, v = c == 'x' ? r : (r & 0x3 | 0x8);
        return v.toString(16);
    });
}

const uuid = generateUUID();
console.log(uuid);
```

这将生成一个类似于 UUID 的字符串，例如 `110e8400-e29b-41d4-a716-446655440000`。

## 深入探讨

在 JavaScript 中生成随机数的主要方法，因而在 TypeScript 中，是 `Math.random()`，它依赖于一个伪随机数生成器 (PRNG)。重要的是要注意，虽然结果看起来是随机的，但它们是基于初始种子值由一个确定性算法生成的。因此，由 `Math.random()` 生成的数字不是真正的随机数，不应该用于加密目的。

对于加密学安全的随机数，Web Crypto API 提供了 `crypto.getRandomValues()`，它在支持 Web Crypto 标准的环境中可访问，包括现代浏览器和 Node.js（通过 `crypto` 模块）。以下是一个快速示例，展示了在 TypeScript 中使用它生成一个安全随机数范围：

```TypeScript
function secureRandom(min: number, max: number): number {
    const array = new Uint32Array(1);
    window.crypto.getRandomValues(array);
    return min + (array[0] % (max - min + 1));
}

const secureRandNum = secureRandom(1, 100);
console.log(secureRandNum);
```

这种方法提供了更强的随机性，更适合安全敏感的应用。然而，它也更消耗资源，并且对于一些更简单的任务，如简单模拟或非关键的随机值生成，可能并不必要。
