---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:58:12.672822-07:00
description: "\u041A\u043E\u043C\u043F\u043B\u0435\u043A\u0441\u043D\u0456 \u0447\u0438\
  \u0441\u043B\u0430, \u0449\u043E \u0441\u043A\u043B\u0430\u0434\u0430\u044E\u0442\
  \u044C\u0441\u044F \u0437 \u0434\u0456\u0439\u0441\u043D\u043E\u0457 \u0456 \u0443\
  \u044F\u0432\u043D\u043E\u0457 \u0447\u0430\u0441\u0442\u0438\u043D\u0438 (\u0437\
  \u0430\u0437\u0432\u0438\u0447\u0430\u0439 \u043F\u043E\u0437\u043D\u0430\u0447\u0430\
  \u044E\u0442\u044C\u0441\u044F \u044F\u043A a + bi), \u0440\u043E\u0437\u0448\u0438\
  \u0440\u044E\u044E\u0442\u044C \u043A\u043E\u043D\u0446\u0435\u043F\u0446\u0456\u044E\
  \ \u0431\u0435\u0437\u0440\u043E\u0437\u043C\u0456\u0440\u043D\u0438\u0445 \u0447\
  \u0438\u0441\u0435\u043B \u0434\u043E \u0434\u0432\u043E\u0432\u0438\u043C\u0456\
  \u0440\u043D\u043E\u0433\u043E\u2026"
lastmod: '2024-03-13T22:44:48.786453-06:00'
model: gpt-4-0125-preview
summary: "\u041A\u043E\u043C\u043F\u043B\u0435\u043A\u0441\u043D\u0456 \u0447\u0438\
  \u0441\u043B\u0430, \u0449\u043E \u0441\u043A\u043B\u0430\u0434\u0430\u044E\u0442\
  \u044C\u0441\u044F \u0437 \u0434\u0456\u0439\u0441\u043D\u043E\u0457 \u0456 \u0443\
  \u044F\u0432\u043D\u043E\u0457 \u0447\u0430\u0441\u0442\u0438\u043D\u0438 (\u0437\
  \u0430\u0437\u0432\u0438\u0447\u0430\u0439 \u043F\u043E\u0437\u043D\u0430\u0447\u0430\
  \u044E\u0442\u044C\u0441\u044F \u044F\u043A a + bi), \u0440\u043E\u0437\u0448\u0438\
  \u0440\u044E\u044E\u0442\u044C \u043A\u043E\u043D\u0446\u0435\u043F\u0446\u0456\u044E\
  \ \u0431\u0435\u0437\u0440\u043E\u0437\u043C\u0456\u0440\u043D\u0438\u0445 \u0447\
  \u0438\u0441\u0435\u043B \u0434\u043E \u0434\u0432\u043E\u0432\u0438\u043C\u0456\
  \u0440\u043D\u043E\u0433\u043E \u043F\u0440\u043E\u0441\u0442\u043E\u0440\u0443."
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 \u043A\u043E\u043C\u043F\u043B\
  \u0435\u043A\u0441\u043D\u0438\u043C\u0438 \u0447\u0438\u0441\u043B\u0430\u043C\u0438"
weight: 14
---

## Як це зробити:
Dart сам по собі не включає вбудовану бібліотеку для комплексних чисел, що потребує або реалізації власного класу комплексних чисел, або використання сторонньої бібліотеки. Популярним вибором для наукових обчислень, який включає підтримку комплексних чисел, є `package:scidart`.

### Реалізація Базового Класу Комплексних Чисел
Для простих операцій ви легко можете визначити власний клас комплексних чисел:

```dart
class Complex {
  final double real;
  final double imaginary;

  Complex(this.real, this.imaginary);

  // Додавання двох комплексних чисел
  Complex operator +(Complex other) {
    return Complex(real + other.real, imaginary + other.imaginary);
  }

  // Рядкове представлення для легкого відлагодження
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

### Використання SciDart для Просунутих Операцій
Для більш складних операцій або коли продуктивність є критичною, `package:scidart` пропонує комплексну підтримку комплексних чисел серед інших функціональностей наукових обчислень. Спочатку додайте SciDart у ваш pubspec.yaml:

```yaml
dependencies:
  scidart: ^0.0.1-dev.9
```

Ось як виконати базові операції з комплексними числами за допомогою SciDart:

```dart
import 'package:scidart/numdart.dart';

void main() {
  // Створення комплексних чисел
  var complexNum1 = Complex(real: 5, imaginary: 3);
  var complexNum2 = Complex(real: 2, imaginary: 7);

  // Додавання
  var sum = complexAdd(complexNum1, complexNum2);
  
  // Множення
  var product = complexMultiply(complexNum1, complexNum2);

  print('Сума: ${sum.toString()}');  // Сума: Complex(real: 7.0, imaginary: 10.0)
  print('Добуток: ${product.toString()}');  // Добуток: Complex(real: -11.0, imaginary: 41.0)
}
```

Ці приклади демонструють базову маніпуляцію та використання комплексних чисел в Dart, як через власну реалізацію, так і через бібліотеку SciDart, підкреслюючи гнучкість і потужність Dart для наукових обчислень.
