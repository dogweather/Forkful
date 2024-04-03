---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:01:30.864722-07:00
description: "Att skicka en HTTP-f\xF6rfr\xE5gan i Google Apps Script handlar om att\
  \ programmatiskt g\xF6ra ett anrop till en extern webbserver eller API. Programmerare\
  \ g\xF6r\u2026"
lastmod: '2024-03-13T22:44:37.434900-06:00'
model: gpt-4-0125-preview
summary: "Att skicka en HTTP-f\xF6rfr\xE5gan i Google Apps Script handlar om att programmatiskt\
  \ g\xF6ra ett anrop till en extern webbserver eller API."
title: "Skicka en HTTP-f\xF6rfr\xE5gan"
weight: 44
---

## Hur:
I Google Apps Script är det primära sättet att skicka en HTTP-förfrågan genom att använda tjänsten `UrlFetchApp`. Denna tjänst tillhandahåller metoder för att göra HTTP GET- och POST-begäranden. Här är ett enkelt exempel på att göra en GET-förfrågan för att hämta JSON-data:

```javascript
function fetchJsonData() {
  var url = 'https://api.example.com/data';
  var response = UrlFetchApp.fetch(url);
  var json = response.getContentText();
  var data = JSON.parse(json);
  
  Logger.log(data);
}
```

För en POST-förfrågan, som vanligtvis används för att skicka data till en server, behöver du inkludera fler detaljer i optionsparametern:

```javascript
function postExample() {
  var url = 'https://api.example.com/post';
  var payload = {
    key1: 'value1',
    key2: 'value2'
  };
  
  var options = {
    'method' : 'post',
    'contentType': 'application/json',
    // Konvertera JavaScript-objektet till en JSON-sträng
    'payload' : JSON.stringify(payload)
  };
  
  var response = UrlFetchApp.fetch(url, options);
  Logger.log(response.getContentText());
}
```

Dessa kodsnuttar visar grundläggande implementeringar av GET- och POST-förfrågningar. Resultatet kommer att bero på API-svaret och kan ses i Google Apps Scripts Logger.

## Fördjupning
Google Apps Scripts tjänst `UrlFetchApp` har utvecklats avsevärt sedan dess början, och erbjuder mer nyanserad kontroll över HTTP-förfrågningar med funktioner som att ställa in headers, payload och hantera multipart/form-data för filuppladdningar. Även om det ger ett enkelt sätt att integrera externa webbtjänster, kan utvecklare som kommer från mer robusta backend-språk finna dess funktionalitet något begränsad jämfört med bibliotek som Pythons `requests` eller JavaScripts `fetch` API i Node.js.

En anmärkningsvärd begränsning är exekveringstidsgränsen för Google Apps Script, vilket påverkar långvariga förfrågningar. Dessutom, även om `UrlFetchApp` täcker ett brett spektrum av användningsfall, kan mer komplexa scenarier som involverar OAuth-autentisering eller hantering av mycket stora datamängder kräva kreativa lösningar eller användning av ytterligare Google Cloud-resurser.

Dock, för de flesta integrationer som Google Workspace-utvecklare stöter på—från att automatisera datahämtning till att posta uppdateringar till externa tjänster—tillhandahåller `UrlFetchApp` ett kraftfullt, tillgängligt verktyg. Dess integration i Google Apps Script innebär att det inte behövs några externa bibliotek eller komplexa inställningar, vilket gör HTTP-förfrågningar relativt enkla att utföra inom ramarna för Google Apps Script. I takt med att landskapet av webb-API:er fortsätter att expandera, förblir `UrlFetchApp` en kritisk bro för Google Apps Script-program att interagera med världen utanför Googles ekosystem.
