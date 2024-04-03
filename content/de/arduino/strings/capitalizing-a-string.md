---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:06.961671-07:00
description: "Das Kapitalisieren eines Strings bedeutet, den ersten Buchstaben jedes\
  \ Wortes in einem String in Gro\xDFbuchstaben umzuwandeln, w\xE4hrend sichergestellt\
  \ wird,\u2026"
lastmod: '2024-03-13T22:44:54.128786-06:00'
model: gpt-4-0125-preview
summary: "Das Kapitalisieren eines Strings bedeutet, den ersten Buchstaben jedes Wortes\
  \ in einem String in Gro\xDFbuchstaben umzuwandeln, w\xE4hrend sichergestellt wird,\
  \ dass der Rest klein bleibt."
title: "Einen String gro\xDFschreiben"
weight: 2
---

## Wie:
Arduino, hauptsächlich bekannt für die Interaktion mit Hardware, bietet auch grundlegende Möglichkeiten zur String-Manipulation durch sein `String`-Objekt. Es fehlt jedoch eine direkte `capitalize`-Funktion, wie sie in höheren Programmiersprachen zu sehen ist. Daher implementieren wir die Kapitalisierung durch Iterieren über einen String und Anwendung von Fallumwandlungen.

Hier ist ein einfaches Beispiel ohne die Verwendung von Drittanbieter-Bibliotheken:

```cpp
String capitalizeString(String input) {
  if (input.length() == 0) {
    return ""; // Gibt einen leeren String zurück, wenn die Eingabe leer ist
  }
  input.toLowerCase(); // Wandelt den gesamten String zuerst in Kleinbuchstaben um
  input.setCharAt(0, input.charAt(0) - 32); // Kapitalisiert den ersten Buchstaben
  
  // Kapitalisiert Buchstaben, die auf ein Leerzeichen folgen
  for (int i = 1; i < input.length(); i++) {
    if (input.charAt(i - 1) == ' ') {
      input.setCharAt(i, input.charAt(i) - 32);
    }
  }
  return input;
}

void setup() {
  Serial.begin(9600);
  String testStr = "hello arduino world";
  String capitalizedStr = capitalizeString(testStr);
  Serial.println(capitalizedStr); // Ausgabe: "Hello Arduino World"
}

void loop() {
  // Leere Schleife
}
```

Dieser Code-Ausschnitt definiert eine `capitalizeString`-Funktion, die den gesamten String zuerst in Kleinbuchstaben umwandelt, um seine Schreibweise zu standardisieren. Anschließend wird der erste Buchstabe und jeder Buchstabe, der auf ein Leerzeichen folgt, großgeschrieben, was effektiv jedes Wort im Eingabestring kapitalisiert. Beachten Sie, dass diese rudimentäre Implementierung von der ASCII-Zeichenkodierung ausgeht und möglicherweise Anpassungen für die vollständige Unterstützung von Unicode benötigt.

Derzeit gibt es keine weit verbreiteten Drittanbieter-Bibliotheken speziell für die String-Manipulation im Arduino-Ökosystem, hauptsächlich aufgrund seines Schwerpunkts auf Hardware-Interaktion und Effizienz. Das bereitgestellte Beispiel bietet jedoch eine unkomplizierte Möglichkeit, die Kapitalisierung von Strings innerhalb der Arduino-Programmierumgebung zu erreichen.
