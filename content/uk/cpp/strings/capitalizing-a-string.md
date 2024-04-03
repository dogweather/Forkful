---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:27.978954-07:00
description: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F\
  \ \u0440\u044F\u0434\u043A\u0430 \u043D\u0430 \u0437\u0430\u0433\u043E\u043B\u043E\
  \u0432\u043D\u0438\u0439 \u0440\u0435\u0433\u0456\u0441\u0442\u0440 \u043F\u0435\
  \u0440\u0435\u0434\u0431\u0430\u0447\u0430\u0454 \u043F\u0435\u0440\u0435\u0442\u0432\
  \u043E\u0440\u0435\u043D\u043D\u044F \u043F\u043E\u0447\u0430\u0442\u043A\u043E\u0432\
  \u043E\u0433\u043E \u0441\u0438\u043C\u0432\u043E\u043B\u0430 \u043A\u043E\u0436\
  \u043D\u043E\u0433\u043E \u0441\u043B\u043E\u0432\u0430 \u0443 \u0440\u044F\u0434\
  \u043A\u0443 \u043D\u0430 \u0432\u0435\u043B\u0438\u043A\u0443 \u043B\u0456\u0442\
  \u0435\u0440\u0443, \u044F\u043A\u0449\u043E \u0432\u0456\u043D \u0443 \u043D\u0438\
  \u0436\u043D\u044C\u043E\u043C\u0443 \u0440\u0435\u0433\u0456\u0441\u0442\u0440\u0456\
  ,\u2026"
lastmod: '2024-03-13T22:44:49.812794-06:00'
model: gpt-4-0125-preview
summary: "\u041F\u0435\u0440\u0435\u0442\u0432\u043E\u0440\u0435\u043D\u043D\u044F\
  \ \u0440\u044F\u0434\u043A\u0430 \u043D\u0430 \u0437\u0430\u0433\u043E\u043B\u043E\
  \u0432\u043D\u0438\u0439 \u0440\u0435\u0433\u0456\u0441\u0442\u0440 \u043F\u0435\
  \u0440\u0435\u0434\u0431\u0430\u0447\u0430\u0454 \u043F\u0435\u0440\u0435\u0442\u0432\
  \u043E\u0440\u0435\u043D\u043D\u044F \u043F\u043E\u0447\u0430\u0442\u043A\u043E\u0432\
  \u043E\u0433\u043E \u0441\u0438\u043C\u0432\u043E\u043B\u0430 \u043A\u043E\u0436\
  \u043D\u043E\u0433\u043E \u0441\u043B\u043E\u0432\u0430 \u0443 \u0440\u044F\u0434\
  \u043A\u0443 \u043D\u0430 \u0432\u0435\u043B\u0438\u043A\u0443 \u043B\u0456\u0442\
  \u0435\u0440\u0443, \u044F\u043A\u0449\u043E \u0432\u0456\u043D \u0443 \u043D\u0438\
  \u0436\u043D\u044C\u043E\u043C\u0443 \u0440\u0435\u0433\u0456\u0441\u0442\u0440\u0456\
  , \u0437\u0430\u043B\u0438\u0448\u0430\u044E\u0447\u0438 \u0440\u0435\u0448\u0442\
  \u0443 \u0441\u0438\u043C\u0432\u043E\u043B\u0456\u0432 \u043D\u0435\u0437\u043C\
  \u0456\u043D\u043D\u0438\u043C\u0438."
title: "\u0417\u0440\u043E\u0431\u0438\u0442\u0438 \u043F\u0435\u0440\u0448\u0443\
  \ \u043B\u0456\u0442\u0435\u0440\u0443 \u0440\u044F\u0434\u043A\u0430 \u0432\u0435\
  \u043B\u0438\u043A\u043E\u044E"
weight: 2
---

## Як:
У C++, ви можете зробити рядок заголовним за допомогою стандартної бібліотеки без необхідності використання сторонніх бібліотек. Однак, для більш складних або специфічних поведінок перетворення на заголовний регістр, бібліотеки, як-от Boost, можуть бути дуже корисними. Нижче наведено приклади, що ілюструють обидва підходи.

### Використання стандартної бібліотеки C++:
```cpp
#include <iostream>
#include <cctype> // для std::tolower та std::toupper
#include <string>

std::string capitalizeString(const std::string& input) {
    std::string result;
    bool capitalizeNext = true;

    for (char ch : input) {
        if (std::isspace(ch)) {
            capitalizeNext = true;
        } else if (capitalizeNext) {
            ch = std::toupper(ch);
            capitalizeNext = false;
        }
        result += ch;
    }

    return result;
}

int main() {
    std::string text = "hello world from c++";
    std::string capitalizedText = capitalizeString(text);
    std::cout << capitalizedText << std::endl; // Результат: "Hello World From C++"
}
```

### Використання бібліотеки Boost:
Для більш складної маніпуляції з рядками, включаючи чутливе до локалі перетворення на заголовний регістр, вам може знадобитися використовувати бібліотеку Boost String Algo.

Спочатку переконайтеся, що у вашому проєкті встановлено та налаштовано бібліотеку Boost. Після цього можна підключити необхідні заголовочні файли та використовувати її можливості, як показано нижче.

```cpp
#include <boost/algorithm/string.hpp>
#include <iostream>
#include <string>

int main() {
    std::string text = "hello world from c++";
    std::string capitalizedText = text;

    // перетворює першу літеру кожного слова на велику
    boost::algorithm::to_lower(capitalizedText); // переконуємося, що рядок у нижньому регістрі
    capitalizedText[0] = std::toupper(capitalizedText[0]); // робимо перший символ великою літерою

    for (std::size_t i = 1; i < capitalizedText.length(); ++i) {
        if (isspace(capitalizedText[i - 1])) { // робимо велику літеру після пробілу
            capitalizedText[i] = std::toupper(capitalizedText[i]);
        }
    }

    std::cout << capitalizedText << std::endl; // Результат: "Hello World From C++"
}
```

У цьому випадку, Boost спрощує деякі завдання маніпуляції з рядками, але все ж вимагає спеціального підходу для справжнього перетворення на заголовний регістр, оскільки в основному пропонує утиліти для трансформації та конвертації регістру.
