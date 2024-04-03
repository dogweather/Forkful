---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:44.187452-07:00
description: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 JSON \u0443 Lua \u043F\u043E\
  \u043B\u044F\u0433\u0430\u0454 \u0432 \u0430\u043D\u0430\u043B\u0456\u0437\u0456\
  \ \u0440\u044F\u0434\u043A\u0456\u0432, \u0432\u0456\u0434\u0444\u043E\u0440\u043C\
  \u0430\u0442\u043E\u0432\u0430\u043D\u0438\u0445 \u0443 JSON, \u0434\u043E \u0442\
  \u0430\u0431\u043B\u0438\u0446\u044C Lua \u0456 \u043D\u0430\u0432\u043F\u0430\u043A\
  \u0438, \u0449\u043E \u0434\u043E\u0437\u0432\u043E\u043B\u044F\u0454 \u043B\u0435\
  \u0433\u043A\u043E \u043E\u0431\u043C\u0456\u043D\u044E\u0432\u0430\u0442\u0438\u0441\
  \u044F \u0434\u0430\u043D\u0438\u043C\u0438 \u043C\u0456\u0436 \u043F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u0430\u043C\u0438 Lua\u2026"
lastmod: '2024-03-13T22:44:49.536136-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 JSON \u0443 Lua \u043F\u043E\
  \u043B\u044F\u0433\u0430\u0454 \u0432 \u0430\u043D\u0430\u043B\u0456\u0437\u0456\
  \ \u0440\u044F\u0434\u043A\u0456\u0432, \u0432\u0456\u0434\u0444\u043E\u0440\u043C\
  \u0430\u0442\u043E\u0432\u0430\u043D\u0438\u0445 \u0443 JSON, \u0434\u043E \u0442\
  \u0430\u0431\u043B\u0438\u0446\u044C Lua \u0456 \u043D\u0430\u0432\u043F\u0430\u043A\
  \u0438, \u0449\u043E \u0434\u043E\u0437\u0432\u043E\u043B\u044F\u0454 \u043B\u0435\
  \u0433\u043A\u043E \u043E\u0431\u043C\u0456\u043D\u044E\u0432\u0430\u0442\u0438\u0441\
  \u044F \u0434\u0430\u043D\u0438\u043C\u0438 \u043C\u0456\u0436 \u043F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u0430\u043C\u0438 Lua \u0442\u0430 \u0432\u0435\u0431-\u0441\
  \u043B\u0443\u0436\u0431\u0430\u043C\u0438 \u0430\u0431\u043E \u0437\u043E\u0432\
  \u043D\u0456\u0448\u043D\u0456\u043C\u0438 API."
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 JSON"
weight: 38
---

## Як це зробити:
Lua не включає вбудованої бібліотеки для обробки JSON. Таким чином, однією з популярних сторонніх бібліотек є `dkjson`, яку ви можете легко використовувати для кодування і декодування JSON. Спочатку переконайтеся, що встановили `dkjson`, наприклад, через LuaRocks (`luarocks install dkjson`), а потім слідуйте прикладам нижче.

### Декодування JSON до таблиці Lua
```lua
local dkjson = require "dkjson"

local jsonString = '{"name": "Lua Programmer", "age": 30, "languages": ["Lua", "JavaScript"]}'
local luaTable, pos, err = dkjson.decode(jsonString, 1, nil)
if err then
  print ("Помилка:", err)
else
  print("Ім'я:", luaTable.name) -- Вивід: Ім'я: Lua Programmer
  print("Вік:", luaTable.age) -- Вивід: Вік: 30
  print("Мови:", table.concat(luaTable.languages, ", ")) -- Вивід: Мови: Lua, JavaScript
end
```

### Кодування таблиці Lua в JSON
```lua
local dkjson = require "dkjson"

local luaTable = {
  name = "Lua Programmer",
  age = 30,
  languages = { "Lua", "JavaScript" }
}

local jsonString = dkjson.encode(luaTable, { indent = true })
print(jsonString)
```

Приклад виводу для кодування:
```json
{
  "age": 30,
  "languages": [
    "Lua",
    "JavaScript"
  ],
  "name": "Lua Programmer"
}
```

Ці прості приклади демонструють, як працювати з JSON у Lua, роблячи легким інтеграцію програм Lua з різними веб-технологіями та зовнішніми API. Пам'ятайте, хоча в цих прикладах використовується `dkjson`, інші бібліотеки, такі як `cjson` та `RapidJSON`, також можуть бути підходящими альтернативами залежно від потреб вашого проекту.
