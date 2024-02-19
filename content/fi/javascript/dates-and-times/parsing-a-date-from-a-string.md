---
aliases:
- /fi/javascript/parsing-a-date-from-a-string/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:39.517922-07:00
description: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sennys merkkijonosta mahdollistaa ohjelmoijien\
  \ muuntaa tekstuaaliset p\xE4iv\xE4m\xE4\xE4r\xE4esitykset JavaScriptin `Date`-objekteiksi,\
  \ mik\xE4 helpottaa\u2026"
lastmod: 2024-02-18 23:09:08.045749
model: gpt-4-0125-preview
summary: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sennys merkkijonosta mahdollistaa ohjelmoijien\
  \ muuntaa tekstuaaliset p\xE4iv\xE4m\xE4\xE4r\xE4esitykset JavaScriptin `Date`-objekteiksi,\
  \ mik\xE4 helpottaa\u2026"
title: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sennys merkkijonosta"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Päivämäärän jäsennys merkkijonosta mahdollistaa ohjelmoijien muuntaa tekstuaaliset päivämääräesitykset JavaScriptin `Date`-objekteiksi, mikä helpottaa päivämäärien käsittelyä, vertailua ja muotoiluoperaatioita. Tämä prosessi on olennainen käyttäjän syötteen käsittelyssä, tietokannoista tiedon prosessoinnissa tai työskennellessä API:en kanssa, jotka kommunikoivat päivämääriä merkkijonomuodoissa.

## Kuinka:
JavaScript tarjoaa natiivisti `Date.parse()`-metodin ja `Date`-rakentajan päivämäärämerkkijonojen jäsennykseen. Kuitenkin näillä lähestymistavoilla on rajoituksia ja epäjohdonmukaisuuksia eri selaimissa, erityisesti ei-standardien päivämäärämuotojen kohdalla. Näiden ongelmien ratkaisemiseksi kolmannen osapuolen kirjastot kuten `Moment.js` ja `date-fns` ovat suosittuja niiden luotettavuuden ja käyttömukavuuden ansiosta.

### Käyttäen natiivia JavaScriptiä:
```javascript
const dateString = "2023-04-30T14:55:00";
const dateObj = new Date(dateString);

console.log(dateObj);  // Tuloste: Sun Apr 30 2023 14:55:00 GMT+0000 (Coordinated Universal Time)
```

### Käyttäen Moment.js:
Asenna ensin Moment.js npm:llä tai sisällytä se projektiisi. Sen jälkeen:
```javascript
const moment = require('moment');

const dateString = "2023-04-30T14:55:00";
const dateObj = moment(dateString);

console.log(dateObj.toString());  // Tuloste: Sun Apr 30 2023 14:55:00 GMT+0000
```

### Käyttäen date-fns:
Lisää `date-fns` projektiisi, ja tee päivämäärämerkkijonon jäsentäminen näin:
```javascript
const { parseISO } = require('date-fns');

const dateString = "2023-04-30T14:55:00";
const dateObj = parseISO(dateString);

console.log(dateObj);  // Tuloste: 2023-04-30T14:55:00.000Z
```

Sekä `Moment.js` että `date-fns` tarjoavat laajemmat jäsentämiskyvyt, mukaan lukien erilaisten muotojen ja lokaalien käsittely, mikä tekee niistä suositeltavia monimutkaisiin sovelluksiin.
