---
date: 2024-01-20 17:51:49.616511-07:00
description: "Debug-tulostus auttaa n\xE4kem\xE4\xE4n mit\xE4 ohjelmassasi tapahtuu.\
  \ Sit\xE4 k\xE4ytet\xE4\xE4n virheiden etsint\xE4\xE4n ja ohjelman toiminnan ymm\xE4\
  rt\xE4miseen."
lastmod: '2024-03-13T22:44:56.826437-06:00'
model: gpt-4-1106-preview
summary: "Debug-tulostus auttaa n\xE4kem\xE4\xE4n mit\xE4 ohjelmassasi tapahtuu."
title: "Virheenj\xE4ljitystulosteiden tulostaminen"
weight: 33
---

## How to - Kuinka tehdä:
```Arduino
void setup() {
  Serial.begin(9600); // Käynnistetään sarjayhteys
}

void loop() {
  Serial.println("Tämä on debug-viesti."); // Tulostetaan debug-viesti
  delay(1000); // Viivytetään sekunti
}
```

Esimerkkitulostus:
```
Tämä on debug-viesti.
Tämä on debug-viesti.
...
```

## Deep Dive - Syväsukellus:
Debug-tulostuksen historia juontaa juurensa ohjelmoinnin alkuhämäriin, jolloin se oli yksi harvoista tavoista seurata ohjelman toimintaa reaaliaikaisesti. Vaihtoehtoina debug-tulostukselle ovat muun muassa LEDien vilkuttaminen tai reaaliaikaiset debuggerit. Arduino käyttää sarjaliikennettä (Serial) debug-tulostukseen, mikä on yksinkertaista mutta tehokasta – data kulkee USB:n kautta tietokoneelle, missä voimme lukea sen sarjaportin monitorista.

## See Also - Katso Myös:
- Arduino'n virallinen dokumentaatio Serial-käskystä: https://www.arduino.cc/reference/en/language/functions/communication/serial/
- Arduino debugging techniques: https://www.arduino.cc/en/Tutorial/BuiltInExamples/SerialEvent
- Beginners' guide to Arduino programming: https://www.arduino.cc/en/Guide/HomePage
