---
aliases:
- /fi/typescript/handling-errors/
date: 2024-01-26 00:58:43.438968-07:00
description: "Virheiden k\xE4sittely on odottamattoman odottamista; kyse on siit\xE4\
  , miten selvit\xE4\xE4n, kun koodissamme tapahtuu odottamattomia virheit\xE4. Sen\
  \ avulla pyrimme\u2026"
lastmod: 2024-02-18 23:09:07.326860
model: gpt-4-1106-preview
summary: "Virheiden k\xE4sittely on odottamattoman odottamista; kyse on siit\xE4,\
  \ miten selvit\xE4\xE4n, kun koodissamme tapahtuu odottamattomia virheit\xE4. Sen\
  \ avulla pyrimme\u2026"
title: "Virheiden k\xE4sittely"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Virheiden käsittely on odottamattoman odottamista; kyse on siitä, miten selvitään, kun koodissamme tapahtuu odottamattomia virheitä. Sen avulla pyrimme välttämään kaatumisia ja takaamaan käyttäjille sujuvan kokemuksen, vaikka yllättäviä tilanteita ilmenisikin.

## Kuinka:
TypeScriptissä virheiden käsittelyyn kuuluu usein `try`, `catch`- ja `finally`-lohkot.

```typescript
function riskyOperation() {
  throw new Error("Jotain meni pieleen!");
}

function handleErrors() {
  try {
    riskyOperation();
  } catch (error) {
    console.error("Kaapattu virhe:", error.message);
  } finally {
    console.log("Tämä suoritetaan aina, virheellä tai ilman.");
  }
}

handleErrors();
```

Esimerkkituloste:

```
Kaapattu virhe: Jotain meni pieleen!
Tämä suoritetaan aina, virheellä tai ilman.
```

Asynkroninen esimerkki lupauksilla (promises):

```typescript
async function asyncRiskyOperation() {
  return new Promise((resolve, reject) => {
    // Simuloi virhettä
    reject("Täydellinen epäonnistuminen");
  });
}

async function handleAsyncErrors() {
  try {
    await asyncRiskyOperation();
  } catch (error) {
    console.error("Kaapattu asynkroninen virhe:", error);
  }
}

handleAsyncErrors();
```

Esimerkkituloste:

```
Kaapattu asynkroninen virhe: Täydellinen epäonnistuminen
```

## Syväsukellus
Virheenkäsittely on ollut ohjelmoinnin kulmakivi sen alusta asti. TypeScriptissä, joka rakentuu JavaScriptin päälle, virheenkäsittely vahvistui async/await-toimintojen myötä, jotka otettiin käyttöön ECMAScript 2017:ssä. Sitä ennen me usein turvauduimme callback-funktioihin ja lupauksiin (promises) käsitelläksemme virheitä asynkronisessa koodissa.

Vaihtoehto `try/catch`:lle TypeScriptissä on käyttää virherajoja (error boundaries), joita tarjoavat kehykset, kuten React. Palvelimen puolella virheiden käsittelyssä voidaan käyttää välitysohjelmistoja (middleware) alustoilla, kuten Express.js, virheidenhallinnan keskittämiseksi.

Toteutuksen kannalta TypeScript ei omaa omaa virheenkäsittelymekanismiaan, vaan se käyttää JavaScriptin mekanismeja. Mukautetut virheluokat voivat laajentaa `Error`-luokkaa tarjotakseen kuvailtavampaa virhetietoa.

## Katso Myös
- [MDN try/catch -lauseista](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch)
- [Async/Await MDN:ssä](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await)
- [Virherajojen käyttö Reactissa](https://reactjs.org/docs/error-boundaries.html)
- [Express.js:n virheenkäsittely](https://expressjs.com/en/guide/error-handling.html)
