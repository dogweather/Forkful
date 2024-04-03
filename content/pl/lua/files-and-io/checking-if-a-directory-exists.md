---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:52.524785-07:00
description: "Sprawdzanie, czy katalog istnieje, to podstawowa operacja podczas pisania\
  \ skrypt\xF3w wchodz\u0105cych w interakcj\u0119 z systemem plik\xF3w, zapewniaj\u0105\
  ca, \u017Ce program\u2026"
lastmod: '2024-03-13T22:44:35.554435-06:00'
model: gpt-4-0125-preview
summary: "Sprawdzanie, czy katalog istnieje, to podstawowa operacja podczas pisania\
  \ skrypt\xF3w wchodz\u0105cych w interakcj\u0119 z systemem plik\xF3w, zapewniaj\u0105\
  ca, \u017Ce program dzia\u0142a na prawid\u0142owych \u015Bcie\u017Ckach i zapobiegaj\u0105\
  ca b\u0142\u0119dom zwi\u0105zanym z nieistniej\u0105cymi katalogami."
title: Sprawdzanie, czy katalog istnieje
weight: 20
---

## Jak to zrobić:
W Lua nie masz wbudowanej funkcji, która bezpośrednio sprawdza, czy katalog istnieje, więc często opierasz się na bibliotece Lua File System (lfs), popularnej bibliotece stron trzecich do operacji na plikach.

Najpierw upewnij się, że masz zainstalowany Lua File System. Jeśli nie, możesz go zazwyczaj zainstalować za pomocą LuaRocks:

```sh
luarocks install luafilesystem
```

Następnie możesz użyć poniższego przykładu, aby sprawdzić istnienie katalogu:

```lua
local lfs = require "lfs"

function directoryExists(directory)
    local attr = lfs.attributes(directory)
    return attr and attr.mode == "directory"
end

-- Sprawdź, czy konkretny katalog istnieje
if directoryExists("/path/to/your/directory") then
    print("Katalog istnieje.")
else
    print("Katalog nie istnieje.")
end
```

To wyświetli:

```
Katalog istnieje.
```

Albo, jeśli katalog nie istnieje:

```
Katalog nie istnieje.
```

To podejście wykorzystuje funkcję `lfs.attributes`, aby uzyskać atrybuty ścieżki. Jeśli ścieżka istnieje i jej atrybut `mode` to `directory`, potwierdza to istnienie katalogu.
