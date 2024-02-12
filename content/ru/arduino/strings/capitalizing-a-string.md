---
title:                "Преобразование строки в верхний регистр"
aliases:
- ru/arduino/capitalizing-a-string.md
date:                  2024-01-28T23:55:51.427261-07:00
model:                 gpt-4-0125-preview
simple_title:         "Преобразование строки в верхний регистр"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/arduino/capitalizing-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?

Преобразование строки в верхний регистр означает перевод каждого символа в заглавную букву. Программисты делают это для обеспечения единообразия, особенно в пользовательских интерфейсах или при подготовке данных для хранения или сравнения.

## Как это сделать:

В среде Arduino нет встроенной функции для преобразования всей строки в верхний регистр, поэтому мы напишем простую функцию для этого:

```Arduino
void setup() {
  Serial.begin(9600);
  char example[] = "hello, world!";
  capitalizeString(example);
  Serial.println(example);
}

void loop() {
  // Здесь делать нечего
}

void capitalizeString(char* str) {
  for (int i = 0; str[i] != '\0'; i++) {
    str[i] = toupper((unsigned char)str[i]);
  }
}
```

После запуска скетча выходные данные в мониторе последовательного порта показывают:
```
HELLO, WORLD!
```

## Подробнее

Исторически манипуляции со строками в языках нижнего уровня, таких как C, требуют работы с отдельными символами из-за отсутствия функций высокоуровневой манипуляции со строками. Эта традиция переходит и на производные C++ в Arduino.

Альтернативы включают использование объектов `String`, доступных в C++ Arduino, и вызов метода `.toUpperCase()`. Однако это потребляет больше памяти. Для сред с ограниченной памятью, таких как микроконтроллеры, часто лучше работать с массивами символов в стиле C (строками) и манипулировать этими напрямую.

Детали реализации, о которых нужно помнить при преобразовании строки в верхний регистр в Arduino:
- Убедитесь, что строка является изменяемой (т.е. массивом символов).
- Используйте функцию `toupper` из `<ctype.h>` для преобразования отдельных символов.
- Манипуляция со строками может привести к проблемам с памятью, таким как переполнение буфера, если не обращать внимание на обработку.

## Смотрите также

- Справочник Arduino по методу String `.toUpperCase()`: https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/touppercase/
- Справочник по `toupper` на Cplusplus.com: http://www.cplusplus.com/reference/cctype/toupper/
- Примеры манипуляции со строками в Arduino: https://www.arduino.cc/en/Tutorial/BuiltInExamples/StringAdditionOperator
