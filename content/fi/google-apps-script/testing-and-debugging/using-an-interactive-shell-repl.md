---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:04:11.863400-07:00
description: "Interaktiivinen kuori, eli Read-Eval-Print Loop (REPL), on yksinkertainen\
  \ interaktiivinen ohjelmointiymp\xE4rist\xF6, joka ottaa vastaan yksitt\xE4isi\xE4\
  \ k\xE4ytt\xE4j\xE4n\u2026"
lastmod: '2024-03-13T22:44:56.099034-06:00'
model: gpt-4-0125-preview
summary: "Interaktiivinen kuori, eli Read-Eval-Print Loop (REPL), on yksinkertainen\
  \ interaktiivinen ohjelmointiymp\xE4rist\xF6, joka ottaa vastaan yksitt\xE4isi\xE4\
  \ k\xE4ytt\xE4j\xE4n sy\xF6tteit\xE4 (lausekkeita), arvioi ne ja palauttaa tuloksen\
  \ k\xE4ytt\xE4j\xE4lle."
title: "Interaktiivisen kuoren (REPL) k\xE4ytt\xF6"
weight: 34
---

## Miten:
Google Apps Script, pilvipohjainen skriptikieli Google-tuotteiden tehtävien automatisointiin, ei sisällä sisäänrakennettua REPL-työkalua, kuten esimerkiksi kielissä Python tai JavaScriptin Node.js. Voit kuitenkin jäljitellä samanlaista kokemusta käyttämällä Apps Script Editorin lokitus- ja vianetsintäominaisuuksia tai perustamalla ulkoisen ympäristön. Tässä keskitymme luomaan väliaikaisen REPL:n suoraan Apps Script -editorissa.

1. **Väliaikaisen REPL-toiminnon luominen**:

```javascript
function myREPL() {
  var input = Logger.log('Syötä lausekkeesi: ');
  try {
    var result = eval(input);
    Logger.log('Tulos: ' + result);
  } catch(e) {
    Logger.log('Virhe: ' + e.message);
  }
}
```

Koska suora käyttäjäsyöte ei ole toteutettavissa samalla tavalla kuin perinteisessä REPL:ssä Apps Script -ympäristössä, voit muokata `input`-muuttujaa manuaalisesti ja käynnistää `myREPL()`-funktion lausekkeiden testaamiseksi.

2. **Esimerkkikoodin suoritus**:

Oletetaan, että haluat arvioida `2+2`. Muokkaisit `myREPL`-funktiota seuraavasti:

```javascript
function myREPL() {
  var input = '2+2'; // Syötä lausekkeesi tähän manuaalisesti
  // Loput pysyvät samoina...
}
```

Suoritettuasi `myREPL()`-funktion, tarkista Lokit (Näkymä > Lokit) tulosteelle, joka pitäisi näyttää jotakin tällaista:

```
[20-xx-xxxx xx:xx:xx:xxx] Syötä lausekkeesi:
[20-xx-xxxx xx:xx:xx:xxx] Tulos: 4
```

3. **Vianetsintä Loggerin avulla**:

Monimutkaisemman vianetsinnän yhteydessä voit lisätä `Logger.log(muuttuja);` koodiisi muuttujan tilojen tulostamiseksi, mikä auttaa ymmärtämään skriptisi kulun ja välitilat.

## Syväsukellus
REPL:n konsepti on syvällä tietojenkäsittelyn historiassa, juontaen juurensa 1960-luvun aikajakojärjestelmiin, jotka mahdollistivat interaktiiviset istunnot. Kielet, kuten Lisp, kukoistivat tässä ympäristössä, sillä REPL oli kriittinen niiden iteratiivisessa kehitysprosessissa. Toisin kuin Google Apps Script, joka on kehitetty paljon myöhemmin ja pääasiassa webiä varten, keskittyen Google-sarjan tehtävien automatisointiin iteratiivisen, konsolipohjaisen ohjelmoinnin sijaan.

Google Apps Script ei perinteisesti tue reaaliaikaisia, interaktiivisia koodaussessioita suoraan laatikosta johtuen sen pilvipohjaisesta luonteesta ja web-sovellusten käyttöönottoon keskittyvästä fokuksesta. Sen suoritusmalli pyörii funktioiden ympärillä, joita laukaistaan web-tapahtumista, aikaan sidotuista laukaisijoista tai manuaalisesta käynnistyksestä ympäristössä, eikä välittömistä palautesilmukoista, joita REPL tarjoaa.

Vaikka väliaikainen REPL ja vianetsintä Apps Script Editorissa tarjoavat jonkin tason interaktiivisuutta, ne eivät täysin toista perinteisten REPL:ien tarjoamaa välitöntä palautetta ja tehokkuutta, joita monissa ohjelmointikielissä on. Kehittäjät, jotka etsivät aidompaa REPL-kokemusta Google-teknologioiden kanssa, saattavat tutkia ulkoisia JavaScript-ympäristöjä tai Node.js:ää Googlen API:en kanssa. Nämä voivat tarjota responsiivisemman ja interaktiivisemman koodaussession, vaikkakin vaativat enemmän asetusta ja mahdollisesti poikkeamista suorasta Apps Script -ympäristöstä.
