---
title:                "Merkkijonojen yhdistäminen"
date:                  2024-01-20T17:35:39.169899-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonojen yhdistäminen"
programming_language: "TypeScript"
category:             "TypeScript"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/typescript/concatenating-strings.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Yksinkertaisesti sanottuna, merkkijonojen yhdistäminen tarkoittaa niiden liittämistä peräkkäin uudeksi merkkijonoksi. Koodarit tekevät tätä, koska se auttaa luomaan dynaamisia tekstejä, esimerkiksi käyttäjän tervehtimiseen nimellä tai tiedon yhdistämiseen yhdeksi lausekkeeksi.

## Kuinka:
```TypeScript
// Yksinkertainen yhdistäminen käyttäen + -operaattoria
let tervehdys = "Hei " + "maailma!";
console.log(tervehdys); // "Hei maailma!"

// Template-literalit sallivat muuttujien sijoittamisen merkkijonoihin
let nimi = "Pekka";
let tervehdysNimella = `Terve, ${nimi}!`;
console.log(tervehdysNimella); // "Terve, Pekka!"

// Array.join() menetelmä yhdistää merkkijonot taulukosta
let sanat = ["TypeScript", "on", "siistiä!"];
let lause = sanat.join(" ");
console.log(lause); // "TypeScript on siistiä!"
```

## Syväsukellus
Aikoinaan, JavaScriptissä merkkijonojen yhdistäminen tapahtui vain `+` operaattorilla tai `concat()`-metodilla. TypeScript, JavaScriptin yliluokka, seuraa samaa perinnettä, mutta tarjoaa lisäksi kirjaimellisen syntaksin (template literals), joka helpottaa dynaamista yhdistämistä. Vaihtoehtoja yhdistämiseen ovat `Array.join()` ja erilaiset kolmannen osapuolen kirjastojen funktiot. Suorituskykyyn vaikuttaa moni asia, kuten yhdistettävien merkkijonojen pituus ja määrä. Yleensä template-literalit ja `+` operaattori ovat tehokkaimpia pienissä operaatioissa, mutta massiivisissa yhdistelyissä kannattaa mitata suorituskyky tapauskohtaisesti.

## Katso Myös
- MDN Web Docs - merkkijonot ja merkkijonon käyttö [String - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
