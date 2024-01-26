---
title:                "Nedlasting av en nettside"
date:                  2024-01-20T17:44:27.431995-07:00
model:                 gpt-4-1106-preview
simple_title:         "Nedlasting av en nettside"
programming_language: "Lua"
category:             "Lua"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/lua/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å laste ned en nettside betyr å hente HTML-koden til siden slik at vi kan jobbe med den lokalt. Programmerere gjør dette for å analysere innhold, hente data, eller sjekke tilgjengelighet.

## Slik gjør du:
```Lua
-- Last ned en nettside med Lua

-- Sørg for å ha 'socket.http' installert
local http = require("socket.http")
local body, code = http.request("http://www.eksempel.no")

if code == 200 then
    print(body)
else
    print("Kunne ikke laste ned siden, statuskode: " .. code)
end
```
Sample Output:
```
<!DOCTYPE html>
<html>
<head>
    <title>Din Tittel Her</title>
</head>
<body>
    Innholdet på siden...
</body>
</html>
```

## Dypdykk
Før `socket.http` var den greie måten å laste ned nettsider i Lua, brukte programmere ofte kommandolinje-verktøy som `curl` via `os.execute`. Alternativer i Lua verden inkluderer `luasocket`, for enkel tilgang til TCP og UDP sockets, og `lua-requests` for en mere HTTP-sentrisk tilnærming som etterligner Python `requests` modulen. Ved nedlasting håndterer `socket.http` omformingshåndtering og feilkoder, men du må behandle omadresseringer og avansert HTTP funksjonalitet for hånd eller med ekstra biblioteker.

## Se også
- LuaSocket dokumentasjon: http://w3.impa.br/~diego/software/luasocket/
- LuaSec for HTTPS støtte: https://github.com/brunoos/luasec/wiki
- 'lua-requests' for et alternativ som etterligner Python requests: https://github.com/JakobGreen/lua-requests
