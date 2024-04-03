---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:01.542316-07:00
description: "YAML - \u044D\u0442\u043E \u0443\u0434\u043E\u0431\u043D\u044B\u0439\
  \ \u0434\u043B\u044F \u0447\u0435\u043B\u043E\u0432\u0435\u043A\u0430 \u0444\u043E\
  \u0440\u043C\u0430\u0442 \u0441\u0435\u0440\u0438\u0430\u043B\u0438\u0437\u0430\u0446\
  \u0438\u0438 \u0434\u0430\u043D\u043D\u044B\u0445. \u041F\u0440\u043E\u0433\u0440\
  \u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0438\u0441\u043F\u043E\u043B\u044C\u0437\
  \u0443\u044E\u0442 \u0435\u0433\u043E \u0434\u043B\u044F \u0444\u0430\u0439\u043B\
  \u043E\u0432 \u043A\u043E\u043D\u0444\u0438\u0433\u0443\u0440\u0430\u0446\u0438\u0438\
  , \u043E\u0431\u043C\u0435\u043D\u0430 \u0434\u0430\u043D\u043D\u044B\u043C\u0438\
  \ \u0438 \u0445\u0440\u0430\u043D\u0435\u043D\u0438\u044F \u0438\u0437-\u0437\u0430\
  \ \u0435\u0433\u043E\u2026"
lastmod: '2024-03-13T22:44:45.248478-06:00'
model: gpt-4-0125-preview
summary: "YAML - \u044D\u0442\u043E \u0443\u0434\u043E\u0431\u043D\u044B\u0439 \u0434\
  \u043B\u044F \u0447\u0435\u043B\u043E\u0432\u0435\u043A\u0430 \u0444\u043E\u0440\
  \u043C\u0430\u0442 \u0441\u0435\u0440\u0438\u0430\u043B\u0438\u0437\u0430\u0446\u0438\
  \u0438 \u0434\u0430\u043D\u043D\u044B\u0445."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 YAML"
weight: 41
---

## Как:
Чтобы работать с YAML в PHP, вам понадобится расширение `yaml`. Вот быстрый старт:

**Установить расширение YAML** (если оно не установлено):
```bash
pecl install yaml
```

**Загрузка расширения**:
Убедитесь, что ваш `php.ini` включает:
```ini
extension=yaml
```

**Разбор YAML**: 
```php
<?php
$yamlString = "
settings:
  database: MySQL
  host: localhost";

$array = yaml_parse($yamlString);

print_r($array);
```
**Пример выходных данных**:
```
Array
(
    [settings] => Array
        (
            [database] => MySQL
            [host] => localhost
        )
)
```

**Создание YAML**:
```php
<?php
$array = [
  'settings' => [
    'database' => 'MySQL',
    'host' => 'localhost'
  ]
];

$yamlString = yaml_emit($array);
echo $yamlString;
```
**Пример выходных данных**:
```
settings:
  database: MySQL
  host: localhost
```

## Глубокое погружение:
YAML, что расшифровывается как "YAML - это не язык разметки", фокусируется на данных и структурах данных и превосходит там, где языки вроде XML могут быть слишком сложными. Впервые он был выпущен в 2001 году. Альтернативами являются JSON и XML; YAML часто предпочитают за его читабельность для человека. Расширение `yaml` для PHP использует библиотеку `libyaml`, обеспечивая быстрый разбор и создание.

## Смотрите также:
- Официальная документация PHP по расширению YAML: https://www.php.net/manual/ru/book.yaml.php
- Официальный сайт YAML: https://yaml.org
- Сравнение форматов сериализации данных: https://ru.wikipedia.org/wiki/Сравнение_форматов_сериализации_данных
