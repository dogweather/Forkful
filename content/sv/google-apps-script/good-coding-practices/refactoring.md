---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:59:52.934781-07:00
description: "Refaktorisering i programmeringslexikonet refererar till processen att\
  \ omstrukturera befintlig kod\u2014\xE4ndra faktoriseringen utan att \xE4ndra dess\
  \ externa\u2026"
lastmod: '2024-03-13T22:44:37.447951-06:00'
model: gpt-4-0125-preview
summary: "Refaktorisering i programmeringslexikonet refererar till processen att omstrukturera\
  \ befintlig kod\u2014\xE4ndra faktoriseringen utan att \xE4ndra dess externa beteende\u2014\
  f\xF6r att f\xF6rb\xE4ttra icke-funktionella attribut."
title: Refaktorering
weight: 19
---

## Hur man gör:
I Google Apps Script är ett vanligt scenario som gynnar av refaktorisering förenklingen av besvärliga skript som interagerar med Google Kalkylark eller Dokument. Inledningsvis kan skript vara skrivna på ett snabbt och smutsigt sätt för att få resultat snabbt. Över tid, när skriptet växer, blir det otympligt. Låt oss gå igenom ett exempel på refaktorisering för bättre läsbarhet och effektivitet.

**Originalskript:**

```javascript
function logSheetNames() {
  var sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  for (var i = 0; i < sheets.length; i++) {
    Logger.log(sheets[i].getName());
  }
}
```

Denna funktion loggar namnet på varje blad i ett Google Kalkylark. Även om det fungerar bra, använder det föråldrade JavaScript-praxis och saknar klarhet.

**Refaktoriserat skript:**

```javascript
function logSheetNames() {
  const sheets = SpreadsheetApp.getActiveSpreadsheet().getSheets();
  sheets.forEach(sheet => Logger.log(sheet.getName()));
}
```

I den refaktoriserade versionen har vi bytt till att använda `const` för variabler som inte ändras, vilket gör vår avsikt tydligare. Vi har också använt metoden `forEach`, ett modernare och mer koncist sätt att iterera över arrayer, vilket förbättrar läsbarheten.

**Exempelutdata (för båda skripten):**

Utdata i Logger kommer att se ut ungefär så här, med antagandet att ditt Google Kalkylark har två blad med namnen "Kostnader" och "Intäkter":

```
[20-04-2023 10:00:00: INFO] Kostnader
[20-04-2023 10:00:01: INFO] Intäkter
```

Det refaktoriserade skriptet uppnår samma resultat men är renare och enklare att förstå vid en första anblick.

## Djupdykning
Refaktorisering i Google Apps Script ärver delvis sina principer från den bredare programvaruutvecklingspraxis. Det blev mer erkänt och strukturerat som ett koncept i slutet av 1990-talet, framför allt tack vare Martin Fowlers banbrytande bok "Refaktorisering: Förbättring av befintlig kod" (1999), som gav en omfattande guide till olika refaktoreringstekniker. Även om specifikationen för refaktorisering kan variera mellan programmeringsspråk på grund av deras syntaktiska och funktionella skillnader, kvarstår det grundläggande målet detsamma: att förbättra koden utan att ändra dess externa beteende.

I kontexten av Google Apps Script är ett viktigt aspekt att beakta under refaktorisering tjänstekvoterna och begränsningarna som Google pålägger. Effektivt refaktoriserad kod inte bara läses bättre utan kör också snabbare och mer tillförlitligt inom dessa begränsningar. Till exempel kan batchoperationer (`Range.setValues()` istället för att sätta värden en cell i taget) avsevärt minska exekveringstiden och kvotförbrukningen.

Det är dock viktigt att notera att för vissa komplexa projekt kan Google Apps Script falla kort på grund av just dessa begränsningar. I sådana fall kan det vara värt att titta på alternativ som Google Cloud Functions eller Apps Scripts nyare syskon, AppSheet, som kan erbjuda bättre skalbarhet och funktionalitet.

Slutligen, medan refaktorisering är en kritisk färdighet för att underhålla och förbättra Google Apps Script-projekt, är förståelsen för miljöns begränsningar och övervägandet av alternativa lösningar lika viktigt för att leverera effektiv, robust och underhållbar kod.
