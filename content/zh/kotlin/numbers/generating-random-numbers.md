---
title:                "生成随机数"
aliases:
- zh/kotlin/generating-random-numbers.md
date:                  2024-01-27T20:34:39.627992-07:00
model:                 gpt-4-0125-preview
simple_title:         "生成随机数"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/zh/kotlin/generating-random-numbers.md"
---

{{< edit_this_page >}}

## 什么 & 为什么？

在编程中生成随机数意味着创建没有任何可预测模式的数字。程序员这样做是出于各种原因，包括模拟、算法测试、游戏以及安全应用，在这些应用场景中，不可预测性是实现现实或安全结果的关键。

## 如何操作：

Kotlin 通过其标准库提供了一种直接的方式来生成随机数。以下是生成不同类型随机值的方法：

### 生成随机整数

要在特定范围内生成一个随机整数：

```kotlin
import kotlin.random.Random

fun main() {
    val randomNumber = Random.nextInt(1, 100) // 生成一个介于 1 和 99 之间的随机数
    println(randomNumber)
}
```

### 生成随机双精度浮点数

类似地，生成一个随机双精度浮点数：

```kotlin
import kotlin.random.Random

fun main() {
    val randomDouble = Random.nextDouble(1.0, 10.0) // 生成一个介于 1.0 和 10.0 之间的随机双精度浮点数
    println(randomDouble)
}
```

### 生成随机布尔值

生成一个随机布尔值：

```kotlin
import kotlin.random.Random

fun main() {
    val randomBoolean = Random.nextBoolean() // 随机生成真或假
    println(randomBoolean)
}
```

### 播种以获得可复现结果

在需要可复现的随机数序列的情况下（例如，在测试中），你可以为随机数生成器播种：

```kotlin
import kotlin.random.Random

fun main() {
    val seed = 12345L
    val random = Random(seed)
    val randomNumber = random.nextInt(1, 100)
    println(randomNumber)
}
```

## 深入了解

Kotlin 标准库生成随机数的方法在底层利用了 Java 的 `java.util.Random`，确保了易用性和性能的良好结合。然而，需要注意的是，这些方法生成的是伪随机数，这意味着这些数字看起来是随机的，但是通过一个确定性的过程生成的。

对于大多数应用程序，Kotlin 的 `Random` 类提供的随机性是足够的。然而，对于更注重安全的应用程序，如加密学，其中随机性的质量至关重要时，应考虑使用 `java.security.SecureRandom` 替代。SecureRandom 是专门为加密操作设计的，提供了更高质量的随机性，尽管可能会有性能上的折中。

Kotlin 并没有重新发明轮子，而是在 Java 的随机数生成机制上提供了一个更符合 Kotlin 习惯且更简洁的 API，使其在 Kotlin 项目中的使用更加地道和简洁。一如既往，在处理随机性时，程序员应仔细考虑用例，以选择最合适的工具。
