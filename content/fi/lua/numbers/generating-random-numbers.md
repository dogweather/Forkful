---
title:                "Satunnaislukujen generointi"
date:                  2024-01-27T20:34:30.107916-07:00
model:                 gpt-4-0125-preview
simple_title:         "Satunnaislukujen generointi"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/lua/generating-random-numbers.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?

Satunnaislukujen tuottaminen ohjelmoinnissa tarkoittaa arvaamattomien numeeristen arvojen luomista, joita voidaan käyttää monenlaisiin tarkoituksiin, kuten simulaatioihin, peleihin tai turvasovelluksiin. Ohjelmoijat käyttävät tätä ominaisuutta tuodakseen epävarmuutta tai jäljitelläkseen todellisen elämän vaihtelevuutta projekteissaan.

## Kuinka:

Lua tarjoaa sisäänrakennetun tuen satunnaislukujen tuottamiselle `math.random` -funktion kautta. Tätä funktiota voidaan käyttää usealla tavalla riippuen halutusta tuloksesta:

1. **Satunnaisen liukuluvun tuottaminen välillä 0 ja 1:**

```Lua
print(math.random())
```

Esimerkkituloste voisi olla `0.13117647051304`. Jokainen suoritus tuottaa eri arvon.

2. **Satunnaisen kokonaisluvun tuottaminen määritellyllä välillä:**

Tuottaaksesi satunnaisen kokonaisluvun kahden rajan välillä (mukaan lukien), sinun on ensin asetettava siemen käyttäen `math.randomseed(os.time())` muuttuvuutta varten, sitten kutsua `math.random` kahdella argumentilla:

```Lua
math.randomseed(os.time())
print(math.random(1, 10)) -- Tuottaa satunnaisen kokonaisluvun 1 ja 10 välillä
```

Esimerkkituloste voisi olla `7`. Jälleen, tulos vaihtelee jokaisella suorituksella.

On ratkaisevan tärkeää asettaa siemen `math.randomseed` avulla, koska ilman sitä `math.random` saattaisi tuottaa saman sekvenssin numeroita joka kerta, kun ohjelmaa suoritetaan. Tyypillisesti, siementäminen nykyisellä ajalla, `os.time()`, varmistaa eri sekvenssit suorituskerralla.

## Syväsukellus

Mekanismi, joka on Lua:n (ja useimpien ohjelmointikielten) satunnaislukujen tuottamisen taustalla, ei ole todella satunnainen, vaan pseudosatunnainen, ja sen generoi algoritmi. Nämä pseudosatunnaislukugeneraattorit (PRNG) ovat deterministisiä ja vaativat siemenarvon aloittaakseen lukujen sarjan tuottamisen. Siementämisen valinta on ratkaisevan tärkeä satunnaisuuden laadun kannalta, minkä vuoksi nykyisen ajan käyttö on yleinen käytäntö.

Historiallisesti Lu’an satunnaislukujen tuottamisen kyvykkyydet ovat kehittyneet. Aiemmat versiot luottivat C-standaardikirjaston `rand()` funktioon, jonka laatu ja suorituskyky vaihtelivat toteutuksissa. Lu’an nykyversio parantaa tätä mahdollisesti käyttämällä robustimpia mekanismeja riippuen taustalla olevasta alustasta, tarjoten suuremman johdonmukaisuuden ja hyödyn satunnaislukujen tuottamisessa. 

Projekteissa, jotka vaativat kryptograafisen tason satunnaisuutta, sisäänrakennettu Lua-toiminnallisuus ei ehkä riitä PRNG:ien deterministisen luonteen vuoksi. Tällaisissa tapauksissa ohjelmoijat kääntyvät usein ulkoisten kirjastojen tai järjestelmäkohtaisten API:en puoleen, jotka voivat tarjota ei-deterministisiä satunnaislukuja, jotka soveltuvat korkean turvallisuustason sovelluksiin.
