---
date: 2024-01-26 04:46:13.894049-07:00
description: "\u041A\u043E\u043C\u043F\u043B\u0435\u043A\u0441\u043D\u0456 \u0447\u0438\
  \u0441\u043B\u0430 \u0441\u043A\u043B\u0430\u0434\u0430\u044E\u0442\u044C\u0441\u044F\
  \ \u0437 \u0434\u0456\u0439\u0441\u043D\u043E\u0457 \u0442\u0430 \u0443\u044F\u0432\
  \u043D\u043E\u0457 \u0447\u0430\u0441\u0442\u0438\u043D\u0438 (\u043D\u0430\u043F\
  \u0440\u0438\u043A\u043B\u0430\u0434, 3 + 4i). \u041F\u0440\u043E\u0433\u0440\u0430\
  \u043C\u0456\u0441\u0442\u0438 \u0432\u0438\u043A\u043E\u0440\u0438\u0441\u0442\u043E\
  \u0432\u0443\u044E\u0442\u044C \u0457\u0445 \u0443 Swift \u0434\u043B\u044F \u0437\
  \u0430\u0432\u0434\u0430\u043D\u044C, \u0442\u0430\u043A\u0438\u0445 \u044F\u043A\
  \ \u043E\u0431\u0440\u043E\u0431\u043A\u0430\u2026"
lastmod: '2024-03-13T22:44:49.909146-06:00'
model: gpt-4-0125-preview
summary: "\u041A\u043E\u043C\u043F\u043B\u0435\u043A\u0441\u043D\u0456 \u0447\u0438\
  \u0441\u043B\u0430 \u0441\u043A\u043B\u0430\u0434\u0430\u044E\u0442\u044C\u0441\u044F\
  \ \u0437 \u0434\u0456\u0439\u0441\u043D\u043E\u0457 \u0442\u0430 \u0443\u044F\u0432\
  \u043D\u043E\u0457 \u0447\u0430\u0441\u0442\u0438\u043D\u0438 (\u043D\u0430\u043F\
  \u0440\u0438\u043A\u043B\u0430\u0434, 3 + 4i)."
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 \u043A\u043E\u043C\u043F\u043B\
  \u0435\u043A\u0441\u043D\u0438\u043C\u0438 \u0447\u0438\u0441\u043B\u0430\u043C\u0438"
weight: 14
---

## Як це зробити:
Swift не має вбудованої підтримки комплексних чисел, але ми можемо створити власну:

```Swift
struct ComplexNumber {
    var real: Double
    var imaginary: Double
    
    func add(_ other: ComplexNumber) -> ComplexNumber {
        return ComplexNumber(real: real + other.real, imaginary: imaginary + other.imaginary)
    }
    
    // Додаткові методи, як-от віднімання, множення тощо.
}

let first = ComplexNumber(real: 2, imaginary: 3)
let second = ComplexNumber(real: 1, imaginary: 4)
let result = first.add(second)
print("Результат: \(result.real) + \(result.imaginary)i")
// Приклад виводу: Результат: 3.0 + 7.0i
```

## Поглиблено
Комплексні числа з'явилися у 16 столітті у алгебраїчних рівняннях. Вони є життєво важливими в квантовій механіці, теорії керування та багатьох інших областях. Apple's Swift не має стандартної бібліотеки для комплексних чисел, на відміну від мов як Python чи C++. Альтернативи створенню власної включають використання пакету Numerics, який підтримує комплексні числа, або обгортання C++ комплексної бібліотеки за допомогою взаємодії зі Swift.

## Дивіться також
- Swift Numerics: [https://github.com/apple/swift-numerics](https://github.com/apple/swift-numerics)
