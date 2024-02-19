---
aliases:
- /es/lua/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:58.993019-07:00
description: "YAML, abreviatura de \"YAML Ain't Markup Language\" (YAML no es un lenguaje\
  \ de marcado), es un est\xE1ndar de serializaci\xF3n de datos legible por humanos\
  \ que se\u2026"
lastmod: 2024-02-18 23:09:10.141618
model: gpt-4-0125-preview
summary: "YAML, abreviatura de \"YAML Ain't Markup Language\" (YAML no es un lenguaje\
  \ de marcado), es un est\xE1ndar de serializaci\xF3n de datos legible por humanos\
  \ que se\u2026"
title: Trabajando con YAML
---

{{< edit_this_page >}}

## ¿Qué y por qué?

YAML, abreviatura de "YAML Ain't Markup Language" (YAML no es un lenguaje de marcado), es un estándar de serialización de datos legible por humanos que se utiliza a menudo para archivos de configuración e intercambio de datos entre lenguajes. Los programadores aprovechan YAML debido a su simplicidad y legibilidad, lo que lo convierte en una opción preferida para ajustes, configuraciones de aplicaciones diversas o contenido que debería ser editable por no programadores.

## Cómo hacerlo:

Lua no tiene soporte integrado para YAML, pero puedes trabajar con archivos YAML utilizando bibliotecas de terceros como `lyaml`. Esta biblioteca permite la codificación y decodificación de datos YAML con Lua. Primero, necesitarás instalar `lyaml` a través de LuaRocks, el gestor de paquetes de Lua:

```bash
luarocks install lyaml
```

### Decodificando YAML:

Supongamos que tienes el siguiente contenido YAML en un archivo llamado `config.yaml`:

```yaml
database:
  host: localhost
  port: 3306
  username: usuario
  password: contraseña
```

Puedes decodificar este archivo YAML en una tabla de Lua con el siguiente código:

```lua
local yaml = require('lyaml')
local archivo = io.open("config.yaml", "r")
local contenido = archivo:read("*all")
archivo:close()

local datos = yaml.load(contenido)
for k,v in pairs(datos.database) do
  print(k .. ": " .. v)
end
```

Cuando ejecutes este script, debería producir:

```output
host: localhost
port: 3306
username: usuario
password: contraseña
```

### Codificando YAML:

Para codificar tablas de Lua en formato YAML, usas la función `dump` proporcionada por `lyaml`. Considerando que quieres crear una representación YAML de la siguiente tabla de Lua:

```lua
local datos = {
  website = {
    name = "Ejemplo",
    owner = "Jane Doe",
    metadata = {
      creation_date = "2023-01-01",
      tags = {"blog", "personal", "lua"}
    }
  }
}

local yaml = require('lyaml')
local datos_yaml = yaml.dump({datos})
print(datos_yaml)
```

El YAML de salida será:

```yaml
- website:
    metadata:
      creation_date: '2023-01-01'
      tags: [blog, personal, lua]
    name: Ejemplo
    owner: Jane Doe
```

Siguiendo estos patrones, los programadores de Lua pueden gestionar eficazmente los datos de YAML para una variedad de aplicaciones. Estas operaciones con YAML son cruciales para el desarrollo de aplicaciones de Lua versátiles que interactúan sin problemas con otras partes de un sistema o directamente con otros sistemas.
