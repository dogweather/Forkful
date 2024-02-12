---
title:                "Generera slumpmässiga nummer"
aliases:
- /sv/google-apps-script/generating-random-numbers/
date:                  2024-02-01T21:54:07.542056-07:00
model:                 gpt-4-0125-preview
simple_title:         "Generera slumpmässiga nummer"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/google-apps-script/generating-random-numbers.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad och varför?

Att generera slumpmässiga nummer är en grundläggande uppgift inom programmering som används för en mängd olika tillämpningar, såsom simuleringar, spel och säkerhetssystem. Programmerare använder denna teknik i Google Apps Script för att införa variabilitet, testa scenarier och lägga till oförutsägbarhet i sina applikationer inom Googles ekosystem, inklusive Sheets, Docs och Forms.

## Hur man gör:

I Google Apps Script kan du generera slumpmässiga nummer med hjälp av funktionen `Math.random()`, liknande JavaScript. Denna funktion returnerar ett flyttal, pseudo-slumpmässigt nummer i intervallet 0 (inklusive) till 1 (exklusive). För att anpassa dessa nummer för olika användningsområden, som att generera heltal inom ett specifikt intervall, kan du behöva utföra ytterligare beräkningar.

### Generera ett grundläggande slumpmässigt nummer

För att generera ett enkelt slumpmässigt nummer och logga det till konsolen:

```javascript
function generateRandomNumber() {
  var randomNumber = Math.random();
  Logger.log(randomNumber);
}
```
*Exempel på utdata:* `0.1234567890123456`

### Generera ett heltal inom ett specifikt intervall

För att generera ett slumpmässigt heltal mellan två värden (`min` och `max`), inklusive:

```javascript
function getRandomInt(min, max) {
  min = Math.ceil(min);
  max = Math.floor(max);
  var randomNumber = Math.floor(Math.random() * (max - min + 1)) + min;
  Logger.log(randomNumber);
  return randomNumber;
}

// Exempel:
getRandomInt(1, 10);
```
*Exempel på utdata*: `7`

Kom ihåg, `Math.ceil()`-funktionen används för att avrunda det minsta värdet uppåt, och `Math.floor()` används för att avrunda det högsta värdet nedåt, vilket säkerställer att det slumpmässiga numret hamnar inom det angivna intervallet.

## Fördjupning

Mekanismen för att generera slumpmässiga nummer i Google Apps Script, och faktiskt i de flesta programmeringsspråk, utnyttjar en pseudo-slumpmässig nummergenerator (PRNG). Denna teknik är deterministisk och förlitar sig på ett initialt värde, känt som seed, för att producera en sekvens av nummer som verkar slumpmässiga. Även om detta är tillräckligt för många applikationer, är det viktigt att notera att pseudo-slumpmässiga nummer kanske inte är lämpliga där hög säkerhet eller sann slumpmässighet krävs, som i kryptografiska tillämpningar.

Sann slumpmässighet kan uppnås genom hårdvarubaserade slumpmässiga nummergeneratorer eller tjänster som genererar slumpmässighet från naturliga fenomen. Dock, för de flesta dagliga skriptbehov i Google Apps Script, är `Math.random()` tillräckligt.

Historiskt har strävan efter mer effektiva tekniker för generering av slumpmässiga nummer lett till utvecklingen av olika algoritmer, med noterbara exempel som Mersenne Twister och Linear Congruential Generator (LCG). Dock, med tanke på den höga abstraktionsnivån i Google Apps Script, kommer de flesta användare inte behöva implementera dessa algoritmer direkt, men att förstå de underliggande principerna kan hjälpa till att uppskatta vikten och begränsningarna av generering av slumpmässiga nummer i dina skript.
