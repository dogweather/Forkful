---
date: 2024-01-20 17:51:49.348762-07:00
description: "Debug-Ausgaben drucken hei\xDFt, Informationen w\xE4hrend der Laufzeit\
  \ eines Programms zur Problemdiagnose auszugeben. Entwickler nutzen es, um den\u2026"
lastmod: '2024-03-13T22:44:54.146243-06:00'
model: gpt-4-1106-preview
summary: "Debug-Ausgaben drucken hei\xDFt, Informationen w\xE4hrend der Laufzeit eines\
  \ Programms zur Problemdiagnose auszugeben."
title: Debug-Ausgaben drucken
weight: 33
---

## How to:
Ein einfaches Beispiel, um Daten auf der seriellen Schnittstelle auszugeben:

```Arduino
void setup() {
  Serial.begin(9600); // Startet die serielle Kommunikation mit 9600 Baud
}

void loop() {
  Serial.println("Hello, Debug!"); // Druckt eine Nachricht auf der seriellen Konsole
  delay(1000); // Wartet eine Sekunde
}
```

Wenn das Programm läuft, solltest du alle Sekunde "Hello, Debug!" im seriellen Monitor sehen.

## Deep Dive
Das Drucken von Debug-Ausgaben ist so alt wie das Programmieren selbst. Früher wurden Ausgaben auf Papier gedruckt oder an Terminalgeräte gesendet. Heutzutage nutzen wir meist integrierte Entwicklungsumgebungen (IDEs) und serielle Monitore, wie in der Arduino IDE.

Alternativen zum seriellen Debugging sind das Nutzen von LEDs oder LCD-Displays, um den Status des Programms anzuzeigen, besonders nützlich, wenn der serielle Port gerade anderweitig verwendet wird.

Die serielle Ausgabe in Arduino erfolgt über die UART-Schnittstelle (Universal Asynchronous Receiver/Transmitter), welche digitale Pins benutzt (meistens 0 (RX) und 1 (TX)). Es gibt auch erweiterte Bibliotheken wie "SoftwareSerial" für mehr Flexibilität bezüglich der verwendeten Pins.

## See Also
Für weitere Informationen und Debug-Techniken schaue dir bitte die folgenden Links an:

- Arduino Referenz zum Serial: https://www.arduino.cc/reference/de/language/functions/communication/serial/
- SoftwareSerial Bibliothek: https://www.arduino.cc/en/Reference/softwareSerial
- Arduino Debugging Techniques: https://www.arduino.cc/en/Tutorial/LibraryExamples/SoftwareSerialExample
