---
aliases:
- /sv/arduino/checking-if-a-directory-exists/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:06:44.537063-07:00
description: "I sammanhanget av Arduino-programmering \xE4r det viktigt att kontrollera\
  \ om en mapp finns p\xE5 ett SD-kort eller liknande lagringsmodul f\xF6r att kunna\
  \ l\xE4sa\u2026"
lastmod: 2024-02-18 23:08:52.057533
model: gpt-4-0125-preview
summary: "I sammanhanget av Arduino-programmering \xE4r det viktigt att kontrollera\
  \ om en mapp finns p\xE5 ett SD-kort eller liknande lagringsmodul f\xF6r att kunna\
  \ l\xE4sa\u2026"
title: Kontrollera om en katalog existerar
---

{{< edit_this_page >}}

## Vad & Varför?
I sammanhanget av Arduino-programmering är det viktigt att kontrollera om en mapp finns på ett SD-kort eller liknande lagringsmodul för att kunna läsa eller skriva filer utan fel. Denna operation är avgörande för datalogging, konfigurationshantering eller någon uppgift som kräver strukturerad filförvaring, vilket garanterar tillförlitlighet och smidig prestanda i dina applikationer.

## Hur man gör:
Arduino stöder inte komplext filsystemshantering direkt ur lådan. Men, med hjälp av SD-biblioteket, som är en del av standard Arduino IDE, kan du enkelt arbeta med filer och mappar. För att kontrollera om en mapp finns, måste du först initiera SD-kortet och sedan använda `exists()`-metoden från SD-biblioteket.

Först, inkludera SD-biblioteket och deklarera chip-väljarpinnen:

```cpp
#include <SPI.h>
#include <SD.h>

const int chipSelect = 4; // Chip-väljarpin för SD-kortmodulen
```

I din `setup()`-funktion, initiera SD-kortet och kontrollera om mappen finns:

```cpp
void setup() {
  Serial.begin(9600);
  
  if (!SD.begin(chipSelect)) {
    Serial.println("Initialisering misslyckades!");
    return;
  }

  // Kontrollera om mappen finns
  if (SD.exists("/myDir")) {
    Serial.println("Mappen finns.");
  } else {
    Serial.println("Mappen finns inte.");
  }
}
```
I `loop()`-funktionen kan du hålla den tom eller lägga till annan operativ kod vid behov:

```cpp
void loop() {
  // Operativ kod eller hållas tom
}
```

Exempel på utmatning när koden körs skulle vara antingen:

```
Mappen finns.
```
eller

```
Mappen finns inte.
```

Det är viktigt att säkerställa att SD-kortet är korrekt formaterat och att mappvägen `/myDir` överensstämmer med dina specifika behov. Denna grundläggande kontroll är en hörnsten för att utföra mer komplexa operationer med filer och mappar på SD-kort med Arduino.
