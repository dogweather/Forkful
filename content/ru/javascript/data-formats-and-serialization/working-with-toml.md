---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:04:32.741947-07:00
description: "TOML, \u0441\u043E\u043A\u0440\u0430\u0449\u0435\u043D\u0438\u0435 \u043E\
  \u0442 Tom's Obvious, Minimal Language (\u043E\u0447\u0435\u0432\u0438\u0434\u043D\
  \u044B\u0439 \u043C\u0438\u043D\u0438\u043C\u0430\u043B\u0438\u0441\u0442\u0438\u0447\
  \u043D\u044B\u0439 \u044F\u0437\u044B\u043A \u0422\u043E\u043C\u0430), \u043E\u043F\
  \u0440\u0435\u0434\u0435\u043B\u044F\u0435\u0442, \u043A\u0430\u043A \u0441\u0442\
  \u0440\u0443\u043A\u0442\u0443\u0440\u0438\u0440\u043E\u0432\u0430\u0442\u044C \u043A\
  \u043E\u043D\u0444\u0438\u0433\u0443\u0440\u0430\u0446\u0438\u043E\u043D\u043D\u044B\
  \u0435 \u0444\u0430\u0439\u043B\u044B.\u2026"
lastmod: '2024-03-13T22:44:45.801660-06:00'
model: gpt-4-0125-preview
summary: "TOML, \u0441\u043E\u043A\u0440\u0430\u0449\u0435\u043D\u0438\u0435 \u043E\
  \u0442 Tom's Obvious, Minimal Language (\u043E\u0447\u0435\u0432\u0438\u0434\u043D\
  \u044B\u0439 \u043C\u0438\u043D\u0438\u043C\u0430\u043B\u0438\u0441\u0442\u0438\u0447\
  \u043D\u044B\u0439 \u044F\u0437\u044B\u043A \u0422\u043E\u043C\u0430), \u043E\u043F\
  \u0440\u0435\u0434\u0435\u043B\u044F\u0435\u0442, \u043A\u0430\u043A \u0441\u0442\
  \u0440\u0443\u043A\u0442\u0443\u0440\u0438\u0440\u043E\u0432\u0430\u0442\u044C \u043A\
  \u043E\u043D\u0444\u0438\u0433\u0443\u0440\u0430\u0446\u0438\u043E\u043D\u043D\u044B\
  \u0435 \u0444\u0430\u0439\u043B\u044B."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 TOML"
weight: 39
---

## Как:
Чтобы работать с TOML в JavaScript, вам понадобится парсер, такой как `@iarna/toml`. Сначала установите его: `npm install @iarna/toml`. Затем, преобразуйте строку TOML в объект JavaScript или объект JavaScript в строку формата TOML.

```javascript
const toml = require('@iarna/toml');

// Преобразование строки TOML в объект JS
const tomlStr = `
title = "Пример TOML"

[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
`;

const parsedData = toml.parse(tomlStr);
console.log(parsedData);

// Конвертация объекта JS в строку TOML
const jsObject = {
  title: "Пример TOML",
  database: {
    server: "192.168.1.1",
    ports: [8001, 8001, 8002]
  }
};

const tomlString = toml.stringify(jsObject);
console.log(tomlString);
```

## Подробнее
TOML был впервые выпущен в 2013 году Томом Престон-Вернером, одним из сооснователей GitHub. Он был создан для замены других форматов, таких как INI, благодаря более стандартизированному и легкому для разбора формату. JSON и YAML являются альтернативами, но могут быть слишком сложными или слишком гибкими. Преимущество TOML заключается в статической конфигурации, где предпочитается простой и понятный формат. Его дизайн позволяет просто отображать в хеш-таблицу, где ключи и значения соответствуют именам свойств и их значениям. Для более широкого принятия вам может потребоваться интегрировать инструменты, которые могут конвертировать между TOML и другими форматами из-за различной поддержки в экосистемах.

## Смотрите также
- Официальный репозиторий TOML на GitHub: https://github.com/toml-lang/toml
- Сравнение TOML vs. YAML vs. JSON: https://gist.github.com/oconnor663/9aeb4ed56394cb013a20
- npm пакет `@iarna/toml`: https://www.npmjs.com/package/@iarna/toml
