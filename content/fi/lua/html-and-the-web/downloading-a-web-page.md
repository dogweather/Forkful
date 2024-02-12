---
title:                "Verkkosivun lataaminen"
date:                  2024-01-20T17:44:24.694553-07:00
model:                 gpt-4-1106-preview
simple_title:         "Verkkosivun lataaminen"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/lua/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why? (Mikä & Miksi?)
Ladataan verkkosivu tarkoittaa sen sisällön kopioimista paikallisesti. Ohjelmoijat tekevät sen datan jalostukseen, automatisointiin tai backupointiin.

## How to: (Kuinka tehdään:)
```Lua
-- Tarvitaan luotettava HTTP-kirjasto
local http = require("socket.http")

-- Verkkosivun URL-osoitteen määrittely
local url = "http://esimerkki.fi"

-- Sivun lataaminen ja virheiden käsittely
local body, statusCode, headers, statusText = http.request(url)

if statusCode == 200 then
    print("Sivu ladattu onnistuneesti!")
    print(body)  -- Näytä koko sivun sisältö
else
    print("Virhe latauksessa: " .. statusText)
end
```

Output esimerkki:
```
Sivu ladattu onnistuneesti!
<!DOCTYPE html>...
```

## Deep Dive (Sukellus syvyyksiin):
Verkkosivujen lataus muistuttaa selaimen toimintaa, mutta ohjelmoijana voit tehdä sen ilman graafista käyttöliittymää. Historiallisesti ohjelmoijat käyttivät monimutkaisia komentorivityökaluja, kuten "curl" tai "wget". Lua-kielessä on käytettävissä useita HTTP-kirjastoja, kuten "socket.http", joka on osa LuaSocket-moduulia - se on suosittu vaihtoehto verkkoliikenteen käsittelyyn. Vaihtoehtoisesti "luasec" tarjoaa HTTPS-tuen.

Toisin kuin staattisten sivujen lataus, nykyaikaiset dynaamiset sivut voivat vaatia lisää työtä, esimerkiksi ajamista JavaScriptillä tai session hallintaa. Tällaisten tapausten käsittelyyn on tarjolla esimerkiksi "selenium" kirjasto tai siihen rinnastettavat työkalut.

Tärkeää on myös ymmärtää HTTP-protokollan toiminta: statukset (esim. 200 on onnistunut vastaus), otsikot (headers), jotka voivat sisältää hyödyllistä tietoa, ja tietenkin pyyntöjen ja vastausten rakenne.

## See Also (Katso myös):
- LuaSocket dokumentaatio: http://w3.impa.br/~diego/software/luasocket/http.html
- LuaSec, turvallinen verkkoyhteys: https://github.com/brunoos/luasec/wiki
- "curl" komentorivityökalu: https://curl.se/
- "wget" komentorivityökalu: https://www.gnu.org/software/wget/
- HTTP-protokollan ymmärtäminen: https://developer.mozilla.org/en-US/docs/Web/HTTP
