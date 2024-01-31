---
title:                "Praca z XML"
date:                  2024-01-26T04:33:40.553697-07:00
model:                 gpt-4-0125-preview
simple_title:         "Praca z XML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/lua/working-with-xml.md"
---

{{< edit_this_page >}}

## Co i dlaczego?
Praca z XML polega na analizie i manipulowaniu dokumentami XML za pomocą kodu. Programiści robią to, aby czytać, pisać i modyfikować dane w strukturalnym, przenośnym formacie, który jest szeroko stosowany do wymiany i przechowywania danych.

## Jak to zrobić:
Lua nie zawiera natywnej analizy XML, ale istnieją biblioteki takie jak LuaXML i xml2lua, które wykonują tę pracę. Oto szybki przegląd analizowania XML za pomocą xml2lua:

```Lua
local xml2lua = require("xml2lua")
local handler = require("xmlhandler.tree")

local xmlParser = xml2lua.parser(handler)
xmlParser:parse([[<root><book id="123">Programowanie w Lua</book></root>]])

print(handler.root.book._attr.id)  -- Wyświetla: 123
print(handler.root.book[1])        -- Wyświetla: Programowanie w Lua
```

Do zapisywania XML, oto mini przykład z użyciem LuaXML:

```Lua
local luaxml = require("LuaXML")

local xml = xml.new("root")
xml:append("book")[1] = "Programowanie w Lua"
xml.book._attr = {id="123"}

print(xml:tag())  -- Wyświetla: <root><book id="123">Programowanie w Lua</book></root>
```

## Szczegółowa analiza
XML, skrót od Extensible Markup Language, jest standardem w reprezentacji i wymianie danych od połowy lat 90. Nadaje strukturę danym i jest czytelny zarówno dla człowieka, jak i maszyny.

Chociaż JSON i YAML są obecnie preferowane ze względu na ich prostotę, XML pozostaje rozpowszechniony w wielu systemach korporacyjnych i starszych. W Lua, natywne obsługa XML nie jest wbudowana, ponieważ Lua jest zaprojektowana tak, aby była mała i rozszerzalna poprzez moduły.

Biblioteki XML dla Lua, takie jak LuaXML, xml2lua i inne, wypełniają tę lukę. LuaXML zapewnia lekki czytnik i pisarz XML, podczas gdy xml2lua używa podejścia opartego na zdarzeniach, podobnie do parserów SAX. Te biblioteki są zwykle implementowane w czystym Lua dla przenośności, podczas gdy niektóre mogą polegać na C dla wydajności.

Jeśli chodzi o wydajność i zużycie pamięci, biblioteki XML Lua mogą nie być tak szybkie jak te w językach z natywnym wsparciem. Jednak dla większości przypadków użycia w Lua, szczególnie w rozwoju gier lub skryptach dla systemów wbudowanych, te biblioteki dobrze wykonują swoje zadanie bez przeciążania systemu.

## Zobacz także
- LuaXML na GitHubie: https://github.com/LuaDist/luaxml
- xml2lua na GitHubie: https://github.com/manoelcampos/xml2lua
- Lista bibliotek na stronie Lua.org: https://lua-users.org/wiki/LibrariesAndBindings
