---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:43.850039-07:00
description: "Analizar una fecha de una cadena implica convertir representaciones\
  \ textuales de fechas y horas en un formato que se pueda manipular, almacenar o\
  \ comparar\u2026"
lastmod: '2024-03-13T22:44:59.211245-06:00'
model: gpt-4-0125-preview
summary: "Analizar una fecha de una cadena implica convertir representaciones textuales\
  \ de fechas y horas en un formato que se pueda manipular, almacenar o comparar f\xE1\
  cilmente dentro de un programa Lua."
title: Analizando una fecha a partir de una cadena de texto
weight: 30
---

## Cómo hacerlo:
Lua no tiene soporte integrado para la manipulación de fecha y hora más allá de la funcionalidad limitada proporcionada por las funciones `os.date` y `os.time`. Sin embargo, estas pueden aprovecharse para el análisis básico, y para requisitos más complejos, se puede utilizar la biblioteca `luadate`, una biblioteca externa.

**Usando `os.date` y `os.time`:**
```lua
-- Convertir una fecha legible por humanos a un sello de tiempo y viceversa
local dateString = "2023-09-21 15:00:00"
local patron = "(%d+)-(%d+)-(%d+) (%d+):(%d+):(%d+)"
local año, mes, día, hora, minuto, segundo = dateString:match(patron)

local selloDeTiempo = os.time({
  year = año,
  month = mes,
  day = día,
  hour = hora,
  min = minuto,
  sec = segundo
})

-- Convertir el sello de tiempo de vuelta a un formato legible por humanos
local fechaFormateada = os.date("%Y-%m-%d %H:%M:%S", selloDeTiempo)
print(fechaFormateada)  -- Salida: 2023-09-21 15:00:00
```

**Usando `luadate` (biblioteca de terceros):**
Para usar `luadate`, asegúrate de que esté instalada a través de LuaRocks o tu gestor de paquetes de preferencia. `luadate` añade capacidades extensivas de análisis y manipulación de fecha y hora.

```lua
local date = require('date')

-- Analizar directamente una cadena de fecha
local fechaAnalizada = date.parse("2023-09-21 15:00:00")
print(fechaAnalizada:fmt("%Y-%m-%d %H:%M:%S"))  -- Salida: 2023-09-21 15:00:00

-- Añadiendo duraciones
unaSemanaDespués = fechaAnalizada:adddays(7)
print(unaSemanaDespués:fmt("%Y-%m-%d %H:%M:%S"))  -- Salida: 2023-09-28 15:00:00
```

La biblioteca `luadate` ofrece una manera más intuitiva y poderosa de trabajar con fechas, incluyendo el análisis desde cadenas, formateo, y operaciones aritméticas en fechas, lo que simplifica considerablemente trabajar con datos temporales en Lua.
