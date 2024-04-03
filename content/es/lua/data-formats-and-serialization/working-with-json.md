---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:07.498386-07:00
description: "Trabajar con JSON en Lua implica analizar cadenas formateadas en JSON\
  \ hacia y desde tablas de Lua, facilitando el intercambio de datos entre aplicaciones\u2026"
lastmod: '2024-03-13T22:44:59.223973-06:00'
model: gpt-4-0125-preview
summary: Trabajar con JSON en Lua implica analizar cadenas formateadas en JSON hacia
  y desde tablas de Lua, facilitando el intercambio de datos entre aplicaciones Lua
  y servicios web o APIs externas.
title: Trabajando con JSON
weight: 38
---

## Cómo hacerlo:
Lua no incluye una biblioteca incorporada para el procesamiento de JSON. Por lo tanto, una de las bibliotecas de terceros populares es `dkjson`, la cual puedes usar fácilmente para codificar y decodificar JSON. Primero, asegúrate de instalar `dkjson`, por ejemplo, a través de LuaRocks (`luarocks install dkjson`), y luego sigue los ejemplos a continuación.

### Decodificando JSON a Tabla Lua
```lua
local dkjson = require "dkjson"

local jsonString = '{"name": "Programador Lua", "age": 30, "languages": ["Lua", "JavaScript"]}'
local luaTable, pos, err = dkjson.decode(jsonString, 1, nil)
if err then
  print ("Error:", err)
else
  print("Nombre:", luaTable.name) -- Salida: Nombre: Programador Lua
  print("Edad:", luaTable.age) -- Salida: Edad: 30
  print("Idiomas:", table.concat(luaTable.languages, ", ")) -- Salida: Idiomas: Lua, JavaScript
end
```

### Codificando Tabla Lua a JSON
```lua
local dkjson = require "dkjson"

local luaTable = {
  name = "Programador Lua",
  age = 30,
  languages = { "Lua", "JavaScript" }
}

local jsonString = dkjson.encode(luaTable, { indent = true })
print(jsonString)
```

Ejemplo de salida para la codificación:
```json
{
  "age": 30,
  "languages": [
    "Lua",
    "JavaScript"
  ],
  "name": "Programador Lua"
}
```

Estos ejemplos sencillos demuestran cómo trabajar con JSON en Lua, facilitando la integración de aplicaciones Lua con diversas tecnologías web y APIs externas. Recuerda, aunque `dkjson` se usa en estos ejemplos, otras bibliotecas como `cjson` y `RapidJSON` también pueden ser alternativas adecuadas dependiendo de las necesidades de tu proyecto.
