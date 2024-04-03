---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:02:12.897262-07:00
description: "\u041F\u043E\u0438\u0441\u043A \u0438 \u0437\u0430\u043C\u0435\u043D\
  \u0430 \u0442\u0435\u043A\u0441\u0442\u0430 \u043F\u043E\u0437\u0432\u043E\u043B\
  \u044F\u044E\u0442 \u043D\u0430\u0439\u0442\u0438 \u043E\u043F\u0440\u0435\u0434\
  \u0435\u043B\u0435\u043D\u043D\u044B\u0435 \u0441\u0438\u043C\u0432\u043E\u043B\u044B\
  \ \u0438\u043B\u0438 \u0441\u0442\u0440\u043E\u043A\u0438 \u0432 \u0442\u0435\u043A\
  \u0441\u0442\u0435 \u0438 \u0437\u0430\u043C\u0435\u043D\u0438\u0442\u044C \u0438\
  \u0445 \u0447\u0435\u043C-\u0442\u043E \u0434\u0440\u0443\u0433\u0438\u043C. \u041F\
  \u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0434\u0435\u043B\
  \u0430\u044E\u0442 \u044D\u0442\u043E \u0434\u043B\u044F \u043C\u043E\u0434\u0438\
  \u0444\u0438\u043A\u0430\u0446\u0438\u0438 \u043A\u043E\u0434\u0430,\u2026"
lastmod: '2024-03-13T22:44:45.502041-06:00'
model: gpt-4-0125-preview
summary: "\u041F\u043E\u0438\u0441\u043A \u0438 \u0437\u0430\u043C\u0435\u043D\u0430\
  \ \u0442\u0435\u043A\u0441\u0442\u0430 \u043F\u043E\u0437\u0432\u043E\u043B\u044F\
  \u044E\u0442 \u043D\u0430\u0439\u0442\u0438 \u043E\u043F\u0440\u0435\u0434\u0435\
  \u043B\u0435\u043D\u043D\u044B\u0435 \u0441\u0438\u043C\u0432\u043E\u043B\u044B\
  \ \u0438\u043B\u0438 \u0441\u0442\u0440\u043E\u043A\u0438 \u0432 \u0442\u0435\u043A\
  \u0441\u0442\u0435 \u0438 \u0437\u0430\u043C\u0435\u043D\u0438\u0442\u044C \u0438\
  \u0445 \u0447\u0435\u043C-\u0442\u043E \u0434\u0440\u0443\u0433\u0438\u043C."
title: "\u041F\u043E\u0438\u0441\u043A \u0438 \u0437\u0430\u043C\u0435\u043D\u0430\
  \ \u0442\u0435\u043A\u0441\u0442\u0430"
weight: 10
---

## Как это сделать:
Arduino изначально не поддерживает поиск и замену строк так, как это делают высокоуровневые языки. Однако, вы можете работать с массивами символов или использовать класс `String`, который предлагает метод `replace()`. Хотя первый вариант экономит память, второй более прост в использовании. Давайте сосредоточимся на классе `String` для ясности.

```Arduino
void setup() {
  Serial.begin(9600);
  String text = "I like apples and apples are great!";
  text.replace("apples", "oranges");
  Serial.println(text);
}

void loop() {
  // Здесь делать нечего.
}
```

Пример вывода:
```
I like oranges and oranges are great!
```

## Подробнее
В прошлом задачи манипуляции со строками на микроконтроллерах были редкостью — память была ограничена, а приложения проще. В наши дни, благодаря сложным проектам и достаточному объему памяти (благодаря прогрессу в технологии микроконтроллеров), такие утилиты стали достаточно стандартными.

Если вы не хотите использовать класс `String` из-за его динамического использования памяти, которое может вызвать фрагментацию, вы все еще можете искать и заменять в строках стиля C (массивах символов, заканчивающихся нулем) с помощью функций вроде `strchr()`, `strstr()`, и ручного копирования или замены с помощью циклов. Это более сложно, но дает вам больший контроль над памятью.

Например, альтернативный способ замены подстроки может выглядеть так:

```Arduino
void replaceSubstring(char *input, const char *search, const char *replace) {
  char buffer[100];
  char *p;

  // 'strstr' проверяет, является ли 'search' частью 'input'.
  if (!(p = strstr(input, search))) return;

  // Копируем до точки, где найден 'search'.
  strncpy(buffer, input, p - input);
  buffer[p - input] = '\0';

  // Добавляем 'replace' и остальную часть 'input' после 'search'.
  sprintf(buffer+(p - input), "%s%s", replace, p + strlen(search));

  // Выводим результат
  strcpy(input, buffer);
}

void setup() {
  Serial.begin(9600);
  char text[] = "I like apples and apples are great!";
  replaceSubstring(text, "apples", "oranges");
  Serial.println(text);
}

void loop() {
  // Здесь по-прежнему делать нечего.
}
```

Пример вывода:
```
I like oranges and oranges are great!
```

## См. также
- [Arduino Справочник: Объект String](https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/)
- [Arduino Справочник: Функция замены String](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/replace/)
- [Cplusplus.com: Функции строки C](http://www.cplusplus.com/reference/cstring/)
