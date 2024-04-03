---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:46.917383-07:00
description: "Przetwarzanie HTML polega na wydobywaniu danych i informacji z dokument\xF3\
  w HTML, co jest kluczowe dla takich zada\u0144 jak scraping internetowy, analiza\
  \ danych\u2026"
lastmod: '2024-03-13T22:44:35.537782-06:00'
model: gpt-4-0125-preview
summary: "Przetwarzanie HTML polega na wydobywaniu danych i informacji z dokument\xF3\
  w HTML, co jest kluczowe dla takich zada\u0144 jak scraping internetowy, analiza\
  \ danych oraz automatyzacja."
title: "Analiza sk\u0142adniowa HTML"
weight: 43
---

## Jak to zrobić:
Lua nie posiada wbudowanej biblioteki do przetwarzania HTML, ale można wykorzystać biblioteki stron trzecich takie jak `LuaHTML` lub korzystać z powiązań z `libxml2` przez `LuaXML`. Popularnym podejściem jest użycie biblioteki `lua-gumbo` do przetwarzania HTML, która zapewnia proste w użyciu, zgodne z HTML5 możliwości przetwarzania.

### Instalacja lua-gumbo:
Najpierw upewnij się, że `lua-gumbo` jest zainstalowane. Zazwyczaj można je zainstalować za pomocą luarocks:

```sh
luarocks install lua-gumbo
```

### Podstawowe przetwarzanie z lua-gumbo:
Oto jak możesz przetworzyć prosty fragment HTML i wydobyć z niego dane za pomocą `lua-gumbo`:

```lua
local gumbo = require "gumbo"
local document = gumbo.parse([[<html><body><p>Witaj, świecie!</p></body></html>]]

local p = document:getElementsByTagName("p")[1]
print(p.textContent)  -- Wyjście: Witaj, świecie!
```

### Zaawansowany przykład - wydobycie linków:
Aby wydobyć atrybuty `href` ze wszystkich znaczników kotwicy (`<a>`) w dokumencie HTML:

```lua
local gumbo = require "gumbo"
local document = gumbo.parse([[
<html>
<head><title>Przykładowa strona</title></head>
<body>
  <a href="http://przyklad.com/1">Link 1</a>
  <a href="http://przyklad.com/2">Link 2</a>
  <a href="http://przyklad.com/3">Link 3</a>
</body>
</html>
]])

for _, element in ipairs(document.links) do
    if element.getAttribute then  -- Upewnij się, że to Element i ma atrybuty
        local href = element:getAttribute("href")
        if href then print(href) end
    end
end

-- Przykładowe wyjście:
-- http://przyklad.com/1
-- http://przyklad.com/2
-- http://przyklad.com/3
```

Ten fragment kodu iteruje przez wszystkie linki w dokumencie i wyświetla ich atrybuty `href`. Możliwość przetwarzania przez bibliotekę `lua-gumbo` i zrozumienie struktury dokumentu HTML upraszcza proces wydobywania konkretnych elementów na podstawie ich znaczników lub atrybutów.
