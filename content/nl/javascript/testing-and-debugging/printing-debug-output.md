---
aliases:
- /nl/javascript/printing-debug-output/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:35.640748-07:00
description: "Debugoutput afdrukken in JavaScript gaat over het tonen van variabelen,\
  \ fouten of andere informatie die helpt om snel te begrijpen wat je code doet.\u2026"
lastmod: 2024-02-18 23:09:02.278855
model: gpt-4-0125-preview
summary: "Debugoutput afdrukken in JavaScript gaat over het tonen van variabelen,\
  \ fouten of andere informatie die helpt om snel te begrijpen wat je code doet.\u2026"
title: Debug-output afdrukken
---

{{< edit_this_page >}}

## Wat & Waarom?

Debugoutput afdrukken in JavaScript gaat over het tonen van variabelen, fouten of andere informatie die helpt om snel te begrijpen wat je code doet. Programmeurs doen dit om bugs te vangen, de uitvoeringsstroom te begrijpen en te zorgen dat de code doet wat het moet doen.

## Hoe:

JavaScript maakt het ontzettend eenvoudig om debugoutput af te drukken met `console.log()`. Zo doe je dat:

```javascript
console.log('Hallo, debugwereld!');

let number = 42;
console.log('Het nummer is:', number);

function add(a, b) {
  console.log(`Optellen ${a} + ${b}`);
  return a + b;
}

let result = add(3, 4);
console.log('Resultaat:', result);
```

Een voorbeeld van de output in de console van je browser of de Node.js-terminal zou er zo uitzien:

```
Hallo, debugwereld!
Het nummer is: 42
Optellen 3 + 4
Resultaat: 7
```

## Diepere Duik

De `console.log()` methode komt uit de Console API, die al eeuwen een debuggingvriend is in browsers en Node.js-omgevingen. Maar er is meer dan alleen `log`; je hebt `console.warn()`, `console.error()`, en `console.info()`, allemaal sturen ze berichten uit met verschillende ernstniveaus.

Lang geleden gebruikten ontwikkelaars `alert()` voor debugging, maar dat werd snel vervelend - het blokkeert de interactie met de gebruiker door een dialoogvenster te tonen.

Er is ook `console.dir()` die je een JSON-achtige weergave van een object geeft, handig voor diepe inspecties. Als je wilt bijhouden hoe lang iets duurt, zijn `console.time()` en `console.timeEnd()` je maatjes.

Voor wie van een goede, schone output houdt, toont `console.table()` gegevens in een netjes tabelformaat. En wanneer je verder gaat dan eenvoudige debugging en de prestatiewereld betreedt, heeft de Console API nog meer gereedschappen zoals `console.trace()` voor callstack-informatie, `console.profile()` voor prestatieprofilering, onder anderen.

De manier waarop `console`-methoden worden geïmplementeerd kan verschillen tussen JavaScript-omgevingen, maar de essentie blijft hetzelfde: ze helpen ontwikkelaars om snel en met minimale moeite te begrijpen wat er onder de motorkap gebeurt.

## Zie Ook

- MDN Web Docs over Console API: https://developer.mozilla.org/en-US/docs/Web/API/Console
- Node.js `console` documentatie: https://nodejs.org/api/console.html
- Een gids voor console-opdrachten: https://getfirebug.com/wiki/index.php/Console_API
