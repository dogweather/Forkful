---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:58:06.026585-07:00
description: "\u041A\u043E\u043C\u043F\u043B\u0435\u043A\u0441\u043D\u044B\u0435 \u0447\
  \u0438\u0441\u043B\u0430, \u0441\u043E\u0441\u0442\u043E\u044F\u0449\u0438\u0435\
  \ \u0438\u0437 \u0434\u0435\u0439\u0441\u0442\u0432\u0438\u0442\u0435\u043B\u044C\
  \u043D\u043E\u0439 \u0438 \u043C\u043D\u0438\u043C\u043E\u0439 \u0447\u0430\u0441\
  \u0442\u0438 (\u043E\u0431\u044B\u0447\u043D\u043E \u043E\u0431\u043E\u0437\u043D\
  \u0430\u0447\u0430\u0435\u043C\u044B\u0435 \u043A\u0430\u043A a + bi), \u0440\u0430\
  \u0441\u0448\u0438\u0440\u044F\u044E\u0442 \u043F\u043E\u043D\u044F\u0442\u0438\u0435\
  \ \u0431\u0435\u0437\u0440\u0430\u0437\u043C\u0435\u0440\u043D\u044B\u0445 \u0447\
  \u0438\u0441\u0435\u043B \u0434\u043E \u0434\u0432\u0443\u043C\u0435\u0440\u043D\
  \u043E\u0433\u043E\u2026"
lastmod: '2024-03-13T22:44:44.499710-06:00'
model: gpt-4-0125-preview
summary: "\u041A\u043E\u043C\u043F\u043B\u0435\u043A\u0441\u043D\u044B\u0435 \u0447\
  \u0438\u0441\u043B\u0430, \u0441\u043E\u0441\u0442\u043E\u044F\u0449\u0438\u0435\
  \ \u0438\u0437 \u0434\u0435\u0439\u0441\u0442\u0432\u0438\u0442\u0435\u043B\u044C\
  \u043D\u043E\u0439 \u0438 \u043C\u043D\u0438\u043C\u043E\u0439 \u0447\u0430\u0441\
  \u0442\u0438 (\u043E\u0431\u044B\u0447\u043D\u043E \u043E\u0431\u043E\u0437\u043D\
  \u0430\u0447\u0430\u0435\u043C\u044B\u0435 \u043A\u0430\u043A a + bi), \u0440\u0430\
  \u0441\u0448\u0438\u0440\u044F\u044E\u0442 \u043F\u043E\u043D\u044F\u0442\u0438\u0435\
  \ \u0431\u0435\u0437\u0440\u0430\u0437\u043C\u0435\u0440\u043D\u044B\u0445 \u0447\
  \u0438\u0441\u0435\u043B \u0434\u043E \u0434\u0432\u0443\u043C\u0435\u0440\u043D\
  \u043E\u0433\u043E \u043F\u0440\u043E\u0441\u0442\u0440\u0430\u043D\u0441\u0442\u0432\
  \u0430."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 \u043A\u043E\u043C\u043F\u043B\
  \u0435\u043A\u0441\u043D\u044B\u043C\u0438 \u0447\u0438\u0441\u043B\u0430\u043C\u0438"
weight: 14
---

## Как это сделать:
В Dart нет встроенной библиотеки для работы с комплексными числами, что требует либо создания пользовательского класса комплексных чисел, либо использования сторонней библиотеки. Популярным выбором для научных вычислений, включая поддержку комплексных чисел, является `package:scidart`.

### Реализация базового класса комплексного числа
Для простых операций вы можете легко определить свой собственный класс комплексного числа:

```dart
class Complex {
  final double real;
  final double imaginary;

  Complex(this.real, this.imaginary);

  // Сложение двух комплексных чисел
  Complex operator +(Complex other) {
    return Complex(real + other.real, imaginary + other.imaginary);
  }

  // Строковое представление для упрощения отладки
  @override
  String toString() => '${real} + ${imaginary}i';
}

void main() {
  var number1 = Complex(3, 4);
  var number2 = Complex(1, 2);

  var sum = number1 + number2;
  print(sum);  // 4.0 + 6.0i
}
```

### Использование SciDart для сложных операций
Для более сложных операций или когда производительность критична, `package:scidart` предлагает всеобъемлющую поддержку комплексных чисел среди других функций научных вычислений. Сначала добавьте SciDart в ваш pubspec.yaml:

```yaml
dependencies:
  scidart: ^0.0.1-dev.9
```

Вот как выполнять базовые операции с комплексными числами с помощью SciDart:

```dart
import 'package:scidart/numdart.dart';

void main() {
  // Создание комплексных чисел
  var complexNum1 = Complex(real: 5, imaginary: 3);
  var complexNum2 = Complex(real: 2, imaginary: 7);

  // Сложение
  var sum = complexAdd(complexNum1, complexNum2);
  
  // Умножение
  var product = complexMultiply(complexNum1, complexNum2);

  print('Сумма: ${sum.toString()}');  // Сумма: Complex(real: 7.0, imaginary: 10.0)
  print('Произведение: ${product.toString()}');  // Произведение: Complex(real: -11.0, imaginary: 41.0)
}
```

Эти примеры демонстрируют базовое управление и использование комплексных чисел в Dart, как через пользовательскую реализацию, так и через библиотеку SciDart, подчеркивая гибкость и мощь Dart для задач научных вычислений.
