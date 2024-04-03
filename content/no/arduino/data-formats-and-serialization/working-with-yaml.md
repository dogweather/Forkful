---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:28.805058-07:00
description: "YAML (YAML Ain't Markup Language) er en menneskelesbar standard for\
  \ serialisering av data som kan brukes for konfigurasjonsfiler, kommunikasjon mellom\u2026"
lastmod: '2024-03-13T22:44:41.078494-06:00'
model: gpt-4-0125-preview
summary: YAML (YAML Ain't Markup Language) er en menneskelesbar standard for serialisering
  av data som kan brukes for konfigurasjonsfiler, kommunikasjon mellom programmer
  og datalagring.
title: Arbeider med YAML
weight: 41
---

## Hvordan:
Å jobbe direkte med YAML på Arduino er ikke så rett frem som i programmeringsmiljøer på høyere nivå på grunn av begrensninger i minnet og fraværet av innebygde YAML-behandlingsbiblioteker. Imidlertid, for prosjekter som krever YAML-tolkning eller generering, innebærer en typisk tilnærming å bruke en ledsagerdatamaskin (som en Raspberry Pi) eller å konvertere YAML-filer til et mer Arduino-vennlig format (som JSON) ved hjelp av eksterne skript. For demonstrasjonsformål, la oss fokusere på den siste tilnærmingen ved hjelp av et populært bibliotek: ArduinoJson.

**Steg 1:** Konverter din YAML-konfigurasjon til JSON. Du kan bruke nettbaserte verktøy eller kommandolinje-verktøy som `yq`.

YAML-fil (`config.yaml`):
```yaml
wifi:
  ssid: "YourSSID"
  password: "YourPassword"
```

Konvertert til JSON (`config.json`):
```json
{
  "wifi": {
    "ssid": "YourSSID",
    "password": "YourPassword"
  }
}
```

**Steg 2:** Bruk ArduinoJson-biblioteket til å tolke JSON-filen i din Arduino-sketch. Først må du installere ArduinoJson-biblioteket via biblioteksbehandleren i Arduino IDE.

**Steg 3:** Last og tolk JSON i koden din. På grunn av Arduino's lagringsbegrensninger, forestill deg at JSON-strengen er lagret i en variabel eller lest fra et SD-kort.

Eksempel Arduino-sketch:
```cpp
#include <ArduinoJson.h>

const char* jsonConfig = "{\"wifi\":{\"ssid\":\"YourSSID\",\"password\":\"YourPassword\"}}";

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc;
  DeserializationError error = deserializeJson(doc, jsonConfig);

  if (error) {
    Serial.print(F("deserializeJson() feilet: "));
    Serial.println(error.f_str());
    return;
  }

  const char* ssid = doc["wifi"]["ssid"]; // "YourSSID"
  const char* password = doc["wifi"]["password"]; // "YourPassword"

  Serial.print("SSID: ");
  Serial.println(ssid);
  Serial.print("Passord: ");
  Serial.println(password);
}

void loop() {
  // Ingenting her for dette eksempelet
}
```

Output ved kjøring av sketsjen:
```
SSID: YourSSID
Passord: YourPassword
```

Denne tilnærmingen, som involverer konvertering til JSON og utnyttelse av ArduinoJson-biblioteket, gir håndterlig YAML-konfigurasjonsbehandling innenfor Arduino-prosjekter, og omgår direkte YAML-tolkning på mikrokontrolleren.
