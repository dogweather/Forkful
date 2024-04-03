---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:56:03.803271-07:00
description: "Das Logging in der Programmierung beinhaltet das Erfassen von Ereignissen,\
  \ Fehlern oder bemerkenswerten Vorkommnissen w\xE4hrend der Laufzeit. Programmierer\u2026"
lastmod: '2024-03-13T22:44:53.341041-06:00'
model: gpt-4-0125-preview
summary: "Das Logging in der Programmierung beinhaltet das Erfassen von Ereignissen,\
  \ Fehlern oder bemerkenswerten Vorkommnissen w\xE4hrend der Laufzeit."
title: Protokollierung
weight: 17
---

## Wie zu:
In Google Apps Script kann das Logging mit verschiedenen Methoden durchgeführt werden, wie der `Logger`-Klasse und `console.log()`. Die Logger-Klasse ist der traditionelle Weg, geeignet für einfaches Debugging und Entwicklungsansätze. Mit den neuesten Updates bietet `console.log()` mehr Flexibilität und Integration mit Stackdriver Logging, was eine robustere Lösung für die Überwachung Ihrer Apps Scripts in der Google Cloud Platform bereitstellt.

**Logger verwenden:**

```javascript
function logSample() {
  Logger.log('Dies ist eine einfache Log-Nachricht');

  var value = 5;
  Logger.log('Der Wert ist: %s', value); // Zeichenkettenformatierung
}

// Um das Log anzusehen:
// 1. Führen Sie die logSample-Funktion aus.
// 2. Ansicht -> Logs
```

**Beispiel Logger-Ausgabe:**

```
[22-04-20 10:00:00:000 PDT] Dies ist eine einfache Log-Nachricht
[22-04-20 10:00:00:001 PDT] Der Wert ist: 5
```

**console.log() verwenden:**

```javascript
function consoleLogSample() {
  console.log('Diese Nachricht geht an Stackdriver Logging');
  const obj = {name: 'Jane', role: 'Entwickler'};
  console.info('Ein Objekt loggen:', obj);
}

// Logs können in der Google Cloud Platform (GCP)-Konsole unter Stackdriver Logging eingesehen werden
```

**Beispiel console.log()-Ausgabe:**

```
Diese Nachricht geht an Stackdriver Logging
Ein Objekt loggen: {name: "Jane", role: "Entwickler"}
```

Indem man zu `console.log()` für komplexe Anwendungen übergeht, können Entwickler effizient Logs mit Hilfe der leistungsstarken Filter und Werkzeuge, die von GCP bereitgestellt werden, parsen und analysieren, was mit der traditionellen Logger-Klasse nicht so unkompliziert ist.

## Tiefer Einblick:
Das Logging in Google Apps Script hat sich deutlich weiterentwickelt. Ursprünglich war die `Logger`-Klasse die Hauptmethode für Entwickler, um ihre Skripte zu debuggen. Es ist einfach und ausreichend für grundlegende Skripte, es fehlen jedoch die Fähigkeiten, die für moderne Cloud-Anwendungen benötigt werden, wie das Suchen in Logs oder das Analysieren von Log-Trends im Zeitverlauf.

Die Einführung von `console.log()` hat diese Lücke geschlossen, indem es das Logging von Google Apps Script mit Googles Cloud Stackdriver Logging (jetzt als Operations Suite bezeichnet) integriert hat und eine zentralisierte Plattform für das Logging, die Überwachung und das Debugging von Anwendungen bereitstellt. Dies ermöglichte nicht nur das Logging in großem Maßstab, sondern eröffnete auch fortgeschrittene Funktionen für die Log-Verwaltung wie logbasierte Metriken, Echtzeit-Log-Analyse und Integration mit anderen Google Cloud-Diensten.

Während `Logger` nach wie vor einen Zweck für schnelles Debugging und Logging in kleineren Skripten dient, spiegelt die Evolution hin zu `console.log()` eine breitere Verschiebung in der Entwicklung skalierbarer, Cloud-nativer Anwendungen wider. Es unterstreicht Googles Engagement, Entwicklern Werkzeuge zur Verfügung zu stellen, die der Komplexität und dem Umfang heutiger Anwendungen gerecht werden. Allerdings sollten Neulinge sich der etwas steileren Lernkurve bewusst sein und die Notwendigkeit, sich mit Konzepten der Google Cloud Platform vertraut zu machen. Trotzdem ist der Schritt für Entwickler vorteilhaft, die die Cloud-Fähigkeiten voll ausschöpfen möchten. Diese Ausrichtung auf Cloud-Services ist Teil eines breiteren Trends in der Softwareentwicklung, der die Bedeutung robuster, skalierbarer Logging-Mechanismen im Zeitalter des Cloud-Computings hervorhebt.
