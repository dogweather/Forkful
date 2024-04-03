---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:04:08.798319-07:00
description: "Assoziative Arrays, bekannt als Objekte in Google Apps Script (eine\
  \ Variante von JavaScript), erm\xF6glichen es Programmierern, Sammlungen von Schl\xFC\
  ssel-\u2026"
lastmod: '2024-03-13T22:44:53.326148-06:00'
model: gpt-4-0125-preview
summary: "Assoziative Arrays, bekannt als Objekte in Google Apps Script (eine Variante\
  \ von JavaScript), erm\xF6glichen es Programmierern, Sammlungen von Schl\xFCssel-Wert-Paaren\
  \ zu erstellen."
title: Verwendung von assoziativen Arrays
weight: 15
---

## Wie:
In Google Apps Script erstellt und manipuliert man assoziative Arrays (Objekte) mit geschweiften Klammern `{}`, indem man Schlüssel-Wert-Paare darin definiert. Schlüssel sind einzigartige Identifikatoren, und Werte können alles von Zeichenketten und Zahlen bis hin zu komplexeren Objekten oder Funktionen sein. Hier ist ein einfaches Beispiel:

```javascript
function createAssociativeArray() {
  var user = {
    name: "John Doe",
    age: 30,
    email: "johndoe@example.com"
  };

  // Werte zugreifen
  Logger.log(user.name); // Gibt aus: John Doe
  Logger.log(user["email"]); // Gibt aus: johndoe@example.com

  // Neue Schlüssel-Wert-Paare hinzufügen
  user.title = "Softwareentwickler";
  user["country"] = "USA";

  Logger.log(user.title); // Gibt aus: Softwareentwickler

  // Über Schlüssel-Wert-Paare iterieren
  for (var key in user) {
    Logger.log(key + ': ' + user[key]);
  }
}
```

Die Ausgabe für den Iterationsteil könnte wie folgt aussehen:
```
name: John Doe
age: 30
email: johndoe@example.com
title: Softwareentwickler
country: USA
```

Beachten Sie, wie Sie sowohl Punkt-notation als auch Klammer-notation für den Zugriff und das Setzen von Eigenschaften verwenden können. Die Klammer-notation ist besonders nützlich, wenn mit Schlüsseln gearbeitet wird, die dynamisch bestimmt werden oder Zeichen enthalten, die in Identifikatoren nicht zulässig sind.

## Vertiefung
Assoziative Arrays in Form von Objekten sind ein Grundpfeiler von JavaScript und damit auch von Google Apps Script, was dessen prototypbasierten Vererbungsmechanismus widerspiegelt. Im Gegensatz zu Sprachen mit traditionellen assoziativen Arrays oder Wörterbüchern (z. B. Pythons dict) bieten Objekte in Google Apps Script ein flexibles und mächtiges Mittel zur Datenstrukturierung, das von der dynamischen Natur von JavaScript profitiert.

Es ist jedoch wichtig zu beachten, dass die ECMAScript 2015-Spezifikation `Map`- und `Set`-Objekte eingeführt hat, die eine unkompliziertere Handhabung assoziativer Sammlungen mit bestimmten Vorteilen gegenüber Objekten bieten, wie etwa die Beibehaltung der Einfügereihenfolge und eine bessere Leistung für große Datensätze. Obwohl Google Apps Script diese ebenfalls unterstützt, hängt die Wahl zwischen der Verwendung von Objekten oder den neueren `Map`/`Set`-Strukturen von den spezifischen Bedürfnissen und Leistungsüberlegungen ab. Für die meisten Aufgaben mit assoziativen Arrays bieten traditionelle objektbasierte Implementierungen einen vertrauten und vielseitigen Ansatz, aber es ist ratsam, neuere Alternativen zu prüfen, wenn die Komplexität Ihres Skripts zunimmt.
