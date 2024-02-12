---
title:                "Organisering av kode i funksjoner"
aliases:
- no/google-apps-script/organizing-code-into-functions.md
date:                  2024-02-01T21:56:57.574102-07:00
model:                 gpt-4-0125-preview
simple_title:         "Organisering av kode i funksjoner"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/google-apps-script/organizing-code-into-functions.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva og hvorfor?

Å organisere kode i funksjoner handler om å strukturere Google Apps Script-koden din ved å separere logiske segmenter i distinkte blokker, hver med ansvar for en spesifikk oppgave. Programmerere gjør dette for å forbedre lesbarheten, vedlikeholdbarheten og gjenbrukbarheten av koden, og sørge for at komplekse skript er enklere å forstå og feilsøke.

## Hvordan:

I Google Apps Script, som er basert på JavaScript, definerer du funksjoner ved å bruke `function` nøkkelordet, etterfulgt av et unikt funksjonsnavn, parenteser `()` som kan inneholde parametere, og krøllparenteser `{}` som kapsler inn funksjonens kodeblokk. Her er et grunnleggende eksempel:

```javascript
function greetUser() {
  var user = Session.getActiveUser().getEmail();
  Logger.log('Hei, ' + user + '!');
}

greetUser();
```

Eksempel på utskrift:

```
Hei, noen@eksempel.com!
```

Nå, la oss se på et mer praktisk eksempel relatert til Google Sheets der vi separerer funksjonaliteten i to funksjoner: en for å sette opp arket og en annen for å fylle det med data.

```javascript
function setupSheet() {
  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var sheet = ss.getSheets()[0];
  sheet.setName('Salgsdata');
  sheet.appendRow(['Vare', 'Antall', 'Pris']);
}

function populateSheet(data) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('Salgsdata');
  data.forEach(function(row) {
    sheet.appendRow(row);
  });
}

// Initialiser datasett
var salgsData = [
  ['Widgets', 15, 2.5],
  ['Gadgets', 8, 3.75]
];

// Kjør funksjonene
setupSheet();
populateSheet(salgsData);
```

I dette eksempelet forbereder `setupSheet` arket, og `populateSheet` tar et datasett med salgsdata for å fylle arket. Å separere disse bekymringene gjør koden renere og mer tilpasningsdyktig til endringer.

## Dypdykk

Konseptet med å dele opp kode i funksjoner er ikke nytt eller unikt for Google Apps Script; det er en grunnleggende programmeringspraksis som anbefales i nesten alle programmeringsspråk. Historisk sett har funksjoner utviklet seg fra det matematiske konseptet om å kartlegge innganger til utganger, som ble en hjørnestein i strukturert programmering. Denne tilnærmingen fremmer modularitet og kodegjenbruk, og tilbyr klare veier for testing av individuelle deler av skriptet.

Google Apps Script, som er basert på JavaScript, nyter godt av JavaScripts førsteklasses funksjoner, som tillater at funksjoner kan sendes som argumenter, returneres fra andre funksjoner, og tilordnes til variabler. Denne funksjonen åpner for avanserte mønstre som tilbakeringinger og funksjonell programmering, selv om disse mønstrene kan introdusere kompleksitet som kan være unødvendig for enkle automatiseringsoppgaver i Google Apps Script.

For større prosjekter eller mer komplekse applikasjoner, kan utviklere utforske JavaScripts nyere funksjoner som pilerfunksjoner, async/await for asynkrone operasjoner, og til og med TypeScript for statisk typing. TypeScript, spesielt, kan kompileres for å kjøre som Google Apps Script, og tilbyr en vei for utviklere som søker mer robust typekontroll og avanserte objektorienterte funksjoner.

Men for de fleste skriptbehov innen Google Apps-suite, er det å holde seg til enkle, godt organiserte funksjoner som demonstrert, en solid grunnmur. Det er alltid en balansegang mellom å utnytte avanserte funksjoner for effektivitet og å opprettholde enkelhet for vedlikehold og lesbarhet.
