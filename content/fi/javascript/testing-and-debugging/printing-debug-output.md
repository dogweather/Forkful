---
date: 2024-01-20 17:53:18.113790-07:00
description: "JavaScriptissa virheiden j\xE4ljitys (debugging) tarkoittaa koodin suorituksen\
  \ tarkkailua, jotta voidaan ymm\xE4rt\xE4\xE4, miss\xE4 ja miksi virheit\xE4 ilmenee.\u2026"
lastmod: '2024-03-13T22:44:56.952349-06:00'
model: gpt-4-1106-preview
summary: "JavaScriptissa virheiden j\xE4ljitys (debugging) tarkoittaa koodin suorituksen\
  \ tarkkailua, jotta voidaan ymm\xE4rt\xE4\xE4, miss\xE4 ja miksi virheit\xE4 ilmenee."
title: "Virheenj\xE4ljitystulosteiden tulostaminen"
weight: 33
---

## How to: (Kuinka tehdä:)
```Javascript
// Perus console.log esimerkki
console.log('Hei, täällä ollaan!');

// Muuttujien tulostaminen
let vuodenAika = 'kesä';
console.log('Vuodenaika:', vuodenAika);

// Monimutkaisempien tietorakenteiden tulostaminen
let hedelmäkori = ['omena', 'banaani', 'kiivi'];
console.log('Hedelmäkori sisältää:', hedelmäkori);

// Debug-viestin tulostaminen ehdollisen lauseen sisällä
for (let i = 0; i < hedelmäkori.length; i++) {
    console.log(`Hedelmäkori indeksissä ${i}:`, hedelmäkori[i]);
}

// Virheiden käsittely try-catch-lohkossa
try {
  throw new Error('Nyt tuli virhe!');
} catch (error) {
  console.error('Virhe pyydystetty:', error);
}
```
Tuloste:
```
Hei, täällä ollaan!
Vuodenaika: kesä
Hedelmäkori sisältää: (3) ["omena", "banaani", "kiivi"]
Hedelmäkori indeksissä 0: omena
Hedelmäkori indeksissä 1: banaani
Hedelmäkori indeksissä 2: kiivi
Virhe pyydystetty: Error: Nyt tuli virhe!
```

## Deep Dive (Sukellus syvemmälle)
Alkujaan, debuggaus tarkoitti kirjaimellisesti ötököiden poistamista tietokoneen sisältä – oikeasti! 1940-luvulla Grace Hopper löysi kuolleen kovan ja korjasi ensimmäisen tunnetun tietokonebugin. Tänä päivänä, `console.log()` on selaimen konsolilla virhetarkastelun perusväline, mutta on olemassa myös edistyneempiä metodeja, kuten `console.info()`, `console.warn()` ja `console.error()`, jotka tarjoavat lisäkontekstin ja priorisoinnin tulosteille. Näiden lisäksi on kehittäjätyökaluja, jotka tarjoavat visuaalista seurantaa ja suorituskykymittausta – nämä ovat korvaamattomia työkaluja monissa tilanteissa.

Toimintoa voidaan toteuttaa myös kirjastojen, kuten Winston tai Bunyan (Node.js-ympäristössä), avulla, jotka tarjoavat monipuolisemmat loggausominaisuudet, kuten lokitiedostojen kirjoituksen ja loggaustason konfiguroinnin.

## See Also (Katso myös)
- MDN Web Docs `console`: https://developer.mozilla.org/en-US/docs/Web/API/console
- Node.js logging with Winston: https://github.com/winstonjs/winston
- Chrome Developer Tools: https://developers.google.com/web/tools/chrome-devtools
- Debugging Node.js in Visual Studio Code: https://code.visualstudio.com/docs/nodejs/nodejs-debugging
