---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:55:13.772887-07:00
description: "Virheenk\xE4sittely Google Apps Scriptiss\xE4 tarkoittaa poikkeustilanteiden\
  \ tai virheiden ennakointia, kiinniottamista ja niihin vastaamista koodin suorituksen\u2026"
lastmod: '2024-03-13T22:44:56.106042-06:00'
model: gpt-4-0125-preview
summary: "Virheenk\xE4sittely Google Apps Scriptiss\xE4 tarkoittaa poikkeustilanteiden\
  \ tai virheiden ennakointia, kiinniottamista ja niihin vastaamista koodin suorituksen\
  \ aikana."
title: "Virheiden k\xE4sittely"
weight: 16
---

## Kuinka:
Google Apps Script, koska se perustuu JavaScriptiin, mahdollistaa perinteisen `try-catch`-lauseen käytön virheiden käsittelyyn, sekä `finally`-lauseen, jos loppusiivous on tarpeen riippumatta siitä, tapahtuiko virhe tai ei.

```javascript
function myFunction() {
  try {
    // Koodi, joka saattaa aiheuttaa virheen
    var sheet = SpreadsheetApp.getActiveSheet();
    var data = sheet.getRange("A1").getValue();
    if (data === "") {
      throw new Error("Solu A1 on tyhjä.");
    }
    Logger.log(data);
  } catch (e) {
    // Virheenkäsittelykoodi
    Logger.log("Virhe: " + e.message);
  } finally {
    // Siivouskoodi, suoritetaan olipa virhettä tai ei
    Logger.log("Funktio suoritettu.");
  }
}
```

Esimerkkituloste ilman virhettä:
```
[Solun arvo]
Funktio suoritettu.
```

Esimerkkituloste virheellä (olettaen, että A1 on tyhjä):
```
Virhe: Solu A1 on tyhjä.
Funktio suoritettu.
```

Google Apps Script tukee myös omien virheiden heittämistä käyttäen `Error`-objektia ja tarvittaessa tiettyjen virhetyyppien kiinniottamista. Kuitenkaan, edistyneen virheenkategorisoinnin puuttuessa on olennaista tukeutua virheviesteihin tarkkuuden saavuttamiseksi.

## Syväsukellus
Historiallisesti, virheenkäsittely skriptauskielissä, kuten JavaScriptissä (ja siten Google Apps Scriptissä), on ollut vähemmän kehittynyttä verrattuna joihinkin käännetyihin kieliin, jotka tarjoavat ominaisuuksia, kuten yksityiskohtaisia poikkeushierarkioita ja kattavia virheenjäljitystyökaluja. Google Apps Scriptin malli on suhteellisen suoraviivainen, hyödyntäen JavaScriptin `try-catch-finally`-paradigmaa. Tämä yksinkertaisuus on linjassa kielen suunnittelun kanssa, jonka tavoitteena on kehittää ja ottaa nopeasti käyttöön pieniä-keskisuuria sovelluksia Googlen ekosysteemissä, mutta se voi joskus rajoittaa kehittäjiä monimutkaisten virhetilanteiden käsittelyssä.

Monimutkaisemmissa sovelluksissa ohjelmoijat täydentävät usein Google Apps Scriptin natiivia virheenkäsittelyä omilla lokitus- ja virheilmoitusmekanismeilla. Tämä voi sisältää virheiden kirjoittamisen Google Sheetiiin tarkistusta varten tai kolmannen osapuolen lokituspalveluiden käyttämisen Google Apps Scriptin URL Fetch Services -palvelun kautta virhetietojen lähettämiseen skriptiympäristön ulkopuolelle.

Vaikka Google Apps Script saattaakin jäädä jälkeen kielistä, kuten Java tai C#, sisäänrakennetun virheenkäsittelyn monimutkaisuuden ja kyvykkyyksien suhteen, sen integraatio Google-palveluiden kanssa ja `try-catch-finally` -lähestymistavan yksinkertaisuus tekevät siitä tehokkaan työkalun kehittäjille nopeisiin automaatiotehtäviin ja integraatioiden luomiseen Googlen ekosysteemissä. Muista taustoista tulevat kehittäjät saattavat huomata, että haaste ei niinkään ole monimutkaisten virheenkäsittelymallien hallitseminen, vaan saatavilla olevan luovasti hyödyntäminen, jotta heidän skriptinsä ovat vankkoja ja käyttäjäystävällisiä.
