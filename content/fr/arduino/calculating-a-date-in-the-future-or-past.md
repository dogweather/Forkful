---
title:                "Calcul d'une date future ou passée"
date:                  2024-01-20T17:30:43.788819-07:00
model:                 gpt-4-1106-preview
simple_title:         "Calcul d'une date future ou passée"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/arduino/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Calculer une date dans le futur ou le passé revient à trouver une date en ajoutant ou soustrayant des jours à partir d'aujourd'hui. Les programmeurs le font pour des rappels, des délais, et la planification d’événements.

## Comment faire :
Voici un exemple simple pour ajouter des jours à la date actuelle avec une carte Arduino et afficher le résultat sur le moniteur série.

```Arduino
#include <RTClib.h>

RTC_DS1307 rtc;

void setup() {
  Serial.begin(9600);
  if (!rtc.begin()) {
    Serial.println("RTC introuvable");
    while (1);
  }

  if (!rtc.isrunning()) {
    Serial.println("RTC n'est pas en cours d'exécution !");
    rtc.adjust(DateTime(__DATE__, __TIME__));
  }
}

void loop() {
  DateTime now = rtc.now();
  DateTime futureDate = now + TimeSpan(10, 0, 0, 0); // Ajouter 10 jours à la date actuelle

  Serial.print("Date dans 10 jours: ");
  Serial.print(futureDate.day());
  Serial.print("/");
  Serial.print(futureDate.month());
  Serial.print("/");
  Serial.println(futureDate.year());

  delay(10000); // Attendre 10 secondes avant de réafficher
}
```

Sortie d’exemple:
```
Date dans 10 jours: 22/3/2023
```

## Exploration approfondie
La gestion des dates a toujours été un sujet complexe en programmation à cause des différentes unités de temps et des exceptions comme les années bissextiles. L'Arduino utilise souvent des bibliothèques, comme `RTClib` pour les horloges en temps réel (RTC), pour manipuler des dates et des heures. D'autres méthodes incluent les calculs manuels ou l'utilisation des services d'heure réseau (NTP). L'implémentation préférera souvent les bibliothèques externes pour simplifier les calculs et prendre en compte les particularités du calendrier.

## Voir aussi
- Documentation de `RTClib` sur GitHub: [github.com/adafruit/RTClib](https://github.com/adafruit/RTClib)
- Guide Arduino sur les horloges en temps réel (RTC) : [www.arduino.cc/en/Guide/Libraries#rtclibraries](https://www.arduino.cc/en/Guide/Libraries#rtclibraries)