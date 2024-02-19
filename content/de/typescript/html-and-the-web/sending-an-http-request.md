---
aliases:
- /de/typescript/sending-an-http-request/
date: 2024-01-20 18:00:34.997069-07:00
description: "HTTP-Anfragen sind das Werkzeug, um mit Servern zu kommunizieren \u2013\
  \ sie senden Daten und holen Antworten. Programmierer nutzen das, um Webinhalte\
  \ dynamisch\u2026"
lastmod: 2024-02-18 23:09:04.593324
model: gpt-4-1106-preview
summary: "HTTP-Anfragen sind das Werkzeug, um mit Servern zu kommunizieren \u2013\
  \ sie senden Daten und holen Antworten. Programmierer nutzen das, um Webinhalte\
  \ dynamisch\u2026"
title: Einen HTTP-Request senden
---

{{< edit_this_page >}}

## Was & Warum?
HTTP-Anfragen sind das Werkzeug, um mit Servern zu kommunizieren – sie senden Daten und holen Antworten. Programmierer nutzen das, um Webinhalte dynamisch zu laden, APIs anzusprechen oder Daten zu synchronisieren.

## How to:
TypeScript mit Axios:

```typescript
import axios from 'axios';

async function fetchData() {
  try {
    const response = await axios.get('https://api.meineseite.de/daten');
    console.log(response.data);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

Ausgabe:

```json
{
  "users": [
    { "id": 1, "name": "Max Mustermann" },
    { "id": 2, "name": "Erika Musterfrau" }
  ]
}
```

Zum Einrichten von Axios:

1. `npm install axios`
2. Obigen Code in einer `.ts` Datei.

TypeScript mit fetch API:

```typescript
async function fetchData() {
  try {
    const response = await fetch('https://api.meineseite.de/daten');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

fetchData();
```

## Deep Dive
Vor Jahrzehnten starteten HTTP-Anfragen meist nur beim Laden einer Seite. AJAX änderte das: dynamische Anfragen ohne Neuladen. Heute gibt's viele Optionen: `XMLHttpRequest`, `fetch`, diverse Bibliotheken wie `jQuery.ajax`, `axios` oder `superagent`. Bei TypeScript achte man auf Typsicherheit – `axios` und `fetch` können über Generics die Datenstruktur definieren.

## See Also
- MDN zu `fetch`: https://developer.mozilla.org/de/docs/Web/API/Fetch_API
- Axios GitHub Repository: https://github.com/axios/axios
- TypeScript Handbook: https://www.typescriptlang.org/docs/handbook/intro.html
