---
date: 2024-01-26 00:56:09.831006-07:00
description: "Virheiden k\xE4sittely ohjelmoinnissa on odottamattoman odottamista.\
  \ Se on suunnittelutaidetta silt\xE4 varalta, ett\xE4 asiat menev\xE4t pieleen,\
  \ jotta voit pit\xE4\xE4\u2026"
lastmod: '2024-03-13T22:44:56.704358-06:00'
model: gpt-4-1106-preview
summary: "Virheiden k\xE4sittely ohjelmoinnissa on odottamattoman odottamista."
title: "Virheiden k\xE4sittely"
weight: 16
---

## Miten:
Lua käyttää kahta pääfunktiota virheiden käsittelyyn: `pcall` ja `xpcall`. Näin käytät niitä:

```lua
function might_fail()
    if math.random() > 0.5 then
        error("Hups! Jotain meni pieleen.")
    else
        print("Kaikki hyvin!")
    end
end

-- Käyttäen pcall
local success, errorMessage = pcall(might_fail)

if success then
    print("Onnistui!")
else
    print("Saatiin kiinni virhe:", errorMessage)
end

-- Käyttäen xpcall virhekäsittelijän kanssa
function myErrorHandler(err)
    print("Virhekäsittelijä sanoo:", err)
end

local status = xpcall(might_fail, myErrorHandler)
print("Onnistuiko kutsu?", status)
```

Esimerkkitulostus voisi olla:

```
Saatiin kiinni virhe: Hups! Jotain meni pieleen.
Virhekäsittelijä sanoo: Hups! Jotain meni pieleen.
Onnistuiko kutsu? false
```
Tai, jos virhettä ei tapahdu:
```
Kaikki hyvin!
Onnistui!
Kaikki hyvin!
Onnistuiko kutsu? true
```

## Syventävä katsaus
Virheiden käsittely eli "poikkeusten käsittely" ei aina ollut asia. Varhaiset ohjelmat kaatuivat – paljon. Ohjelmoinnin kehittyessä syntyi myös tarve vakaudelle. Luassa lähestymistapa on yksinkertainen verrattuna joihinkin muihin kieliin. Ei ole `try/catch` lohkoja, vain `pcall` ja `xpcall`. Ensimmäinen suojaa funktion kutsua palauttamalla tilan ja mahdollisen virheen. Jälkimmäinen lisää virheenkäsittelyfunktion, joka on hyödyllinen räätälöityä puhdistusta tai lokitusta varten.

Luassa vaihtoehtona on käyttää `assert`, joka voi toimia samankaltaisessa tarkoituksessa heittämällä virheen, jos sen ehto on väärä. Mutta se ei ole yhtä joustava kuin `pcall` monimutkaisissa virheenkäsittelyskenaarioissa.

Sisäisesti `pcall` ja `xpcall` toimivat luomalla "suojatun ympäristön" funktion suorittamiselle. Jos virhe ponnahtaa esiin, ympäristö ottaa sen kiinni ja voi joko käsitellä sen heti tai passittaa sen takaisin ohjelman käsiteltäväksi.

## Katso myös
- Ohjelmointi Lualla -kirja (kolmas painos), saatavilla osoitteessa https://www.lua.org/pil/ perusteellista lukemista virheenkäsittelystä varten (Luku 8.4).
- Virallinen Lua 5.4 Referenssikäsikirja: https://www.lua.org/manual/5.4/ - viimeisin tieto Luasta virheenkäsittelyfunktioista.
- Lua-käyttäjien wiki virheenkäsittelystä: http://lua-users.org/wiki/ErrorHandling – yhteisön näkökulmia ja malleja.
