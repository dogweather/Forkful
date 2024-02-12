---
title:                "HTML analysieren"
date:                  2024-02-01T21:57:13.892292-07:00
model:                 gpt-4-0125-preview
simple_title:         "HTML analysieren"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/google-apps-script/parsing-html.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Das Parsen von HTML in Google Apps Script beinhaltet das Extrahieren von Daten aus HTML-Inhalten, was besonders nützlich ist, wenn man mit Webseiten oder webbasierten Datenquellen interagiert. Programmierer tun dies, um die Datensammlung zu automatisieren, Webinhalte zu manipulieren oder Webfunktionalitäten mit Google Apps wie Sheets und Docs zu integrieren.

## Wie:
Google Apps Script verfügt nicht über eine eingebaute Methode zum Parsen von HTML. Sie können jedoch den `UrlFetchApp`-Dienst nutzen, um HTML-Inhalte abzurufen und dann JavaScript-Methoden oder Regex (reguläre Ausdrücke) für das Parsen zu verwenden. Unten finden Sie ein grundlegendes Beispiel, wie man den Titel-Tag von einer Webseite abruft und parst.

```javascript
function parseHTMLTitle(url) {
  // Abrufen des HTML-Inhalts der Webseite
  const response = UrlFetchApp.fetch(url);
  const htmlContent = response.getContentText();

  // Ein einfaches Regex verwenden, um den Inhalt des <title>-Tags zu finden
  const titleRegex = /<title>(.*?)<\/title>/;
  const match = htmlContent.match(titleRegex);

  // Überprüfen, ob ein Titel gefunden wurde, und diesen zurückgeben
  if (match && match.length > 1) {
    return match[1];
  }

  return 'Kein Titel gefunden';
}

// Beispielverwendung
const url = 'http://example.com';
const pageTitle = parseHTMLTitle(url);
Logger.log(pageTitle); // Gibt den Titel der Webseite aus
```

Für ein ausgefeilteres HTML-Parsing können Sie den `XmlService` nutzen, um das HTML als XML zu parsen. Beachten Sie jedoch, dass dies voraussetzt, dass das HTML wohlgeformtes XML ist, was nicht immer der Fall ist:

```javascript
function parseHTMLUsingXmlService(htmlContent) {
  try {
    const document = XmlService.parse(htmlContent);
    const rootElement = document.getRootElement();
    // Von hier aus mit den XmlService-Methoden durch den XML-Baum navigieren
    // Zum Beispiel, um ein bestimmtes Element oder Attribut zu finden
  } catch(e) {
    Logger.log('Fehler beim Parsen von HTML: ' + e.toString());
  }
}
```

## Vertiefung:
Historisch gesehen war das Parsen von HTML in Umgebungen wie Google Apps Script aufgrund des Fehlens eines Document Object Model (DOM) oder spezialisierter Parsing-Bibliotheken, die in anderen Programmierkontexten üblich sind, herausfordernd. JavaScript in einem Browser hat beispielsweise das DOM sofort verfügbar, und Node.js-Umgebungen haben Zugriff auf eine Fülle von NPM-Paketen wie `cheerio` oder `jsdom` zum Parsen von HTML.

Der Ansatz von Google Apps Script stützt sich stark auf die Nutzung von `UrlFetchApp` für Webanfragen und dann die Manipulation der Antwortdaten mit Regex oder XML-Parsing-Methoden. Obwohl Regex für einfache Parsing-Aufgaben nützlich sein kann, wird es für komplexes HTML aufgrund des Risikos von Fehlern und der potenziell brüchigen Natur des Codes allgemein nicht empfohlen. XML-Parsing mit `XmlService` bietet einen strukturierteren Ansatz, erfordert jedoch wohlgeformtes HTML/XML, was eine Einschränkung darstellen kann, wenn man mit willkürlichen Webseiten umgeht.

Für komplexe Parsing-Anforderungen oder beim Umgang mit schlecht geformtem HTML könnte eine alternative Strategie die Nutzung eines externen Webservices zu Google Apps Script beinhalten. Dieser Service könnte HTML-Inhalte verarbeiten, möglicherweise unter Verwendung einer robusteren Parsing-Technik oder -Bibliothek, und dann die verarbeiteten Daten in einer Form zurückgeben, die von Google Apps Script leicht konsumiert werden kann. Dieser Ansatz führt jedoch Netzwerklatenz und die Komplexität des Managements eines zusätzlichen Webservices ein.

Trotz dieser Herausforderungen bleibt das Parsen von HTML innerhalb von Google Apps Script ein leistungsfähiges Werkzeug, insbesondere wenn es mit anderen Google-Diensten und APIs kombiniert wird, und bietet eine Reihe von Automatisierungsmöglichkeiten, die die Produktivität und die Datenverarbeitungsfähigkeiten erheblich steigern können.
