---
aliases:
- /no/javascript/getting-the-current-date/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:51.705003-07:00
description: "\xC5 hente den gjeldende datoen i JavaScript er en grunnleggende oppgave\
  \ som involverer \xE5 hente og muligens manipulere dagens dato og tid. Programmerere\u2026"
lastmod: 2024-02-18 23:08:54.318906
model: gpt-4-0125-preview
summary: "\xC5 hente den gjeldende datoen i JavaScript er en grunnleggende oppgave\
  \ som involverer \xE5 hente og muligens manipulere dagens dato og tid. Programmerere\u2026"
title: "F\xE5 dagens dato"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å hente den gjeldende datoen i JavaScript er en grunnleggende oppgave som involverer å hente og muligens manipulere dagens dato og tid. Programmerere utfører dette for å vise datoer på nettsteder, i applikasjoner, for å spore brukerinteraksjoner eller for å håndtere tidsfølsomme data.

## Hvordan:
I vanilla JavaScript brukes `Date`-objektet for å jobbe med datoer og tider. Slik kan du hente den gjeldende datoen og tiden:

```javascript
const currentDate = new Date();
console.log(currentDate); // Eksempelutskrift: Fri Apr 14 2023 12:34:56 GMT+0100 (Britisk sommertid)
```

For å bare vise datoen i et mer brukervennlig format, kan du bruke metoder som `toLocaleDateString()`:

```javascript
console.log(currentDate.toLocaleDateString()); // Eksempelutskrift: 4/14/2023
```

For mer kontroll over formatet, er tredjepartsbiblioteker som *Moment.js* eller *date-fns* veldig populære, selv om det er godt å være oppmerksom på at Moment.js nå anses som et arveprosjekt i vedlikeholdsmodus.

Bruke *Moment.js*:

```javascript
const moment = require('moment'); // antar Node.js eller bruk av en modulpakker
const formattedDate = moment().format('YYYY-MM-DD');
console.log(formattedDate); // Eksempelutskrift: 2023-04-14
```

Med *date-fns*, som vektlegger modularisering som lar deg kun importere det du trenger:

```javascript
const { format } = require('date-fns');
const formattedDate = format(new Date(), 'yyyy-MM-dd');
console.log(formattedDate); // Eksempelutskrift: 2023-04-14
```

Hver tilnærming tilbyr ulike nivåer av bekvemmelighet og fleksibilitet for å jobbe med datoer i JavaScript, fra det innebygde `Date`-objektet til mer sofistikerte formaterings- og manipuleringsegenskaper tilgjengelig gjennom biblioteker.
