---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:37.107703-07:00
description: "JSON eller JavaScript Object Notation \xE4r ett l\xE4ttviktigt datautbytesformat,\
  \ vilket g\xF6r det perfekt f\xF6r datalagring eller konfigurationsfiler i Arduino-\u2026"
lastmod: '2024-03-13T22:44:38.189366-06:00'
model: gpt-4-0125-preview
summary: "JSON eller JavaScript Object Notation \xE4r ett l\xE4ttviktigt datautbytesformat,\
  \ vilket g\xF6r det perfekt f\xF6r datalagring eller konfigurationsfiler i Arduino-projekt."
title: Arbeta med JSON
weight: 38
---

## Hur:
För att arbeta med JSON i Arduino är `ArduinoJson`-biblioteket ett populärt val på grund av dess användarvänlighet och effektivitet. Det möjliggör tolkning av JSON-strängar, modifiering av dem och serialisering av objekt tillbaka till JSON-strängar. Så här använder du det:

1. **Installera ArduinoJson-biblioteket**: Använd bibliotekshanteraren i Arduino IDE och installera "ArduinoJson".

2. **Avserialisera en JSON-sträng**: Så här tolkar du en JSON-sträng och extraherar värden.

```cpp
#include <ArduinoJson.h>

const char* json = "{\"sensor\":\"gps\",\"time\":1351824120,\"data\":[48.756080,2.302038]}";

void setup() {
  Serial.begin(9600);
  StaticJsonDocument<200> doc; // Justera storleken enligt JSON-dokumentet
  DeserializationError error = deserializeJson(doc, json);

  if (error) {
    Serial.print(F("deserializeJson() misslyckades: "));
    Serial.println(error.f_str());
    return;
  }

  const char* sensor = doc["sensor"]; // "gps"
  long time = doc["time"]; // 1351824120
  float latitud = doc["data"][0]; // 48.756080
  float longitud = doc["data"][1]; // 2.302038
  
  Serial.println(sensor);
  Serial.println(time);
  Serial.println(latitud, 6);
  Serial.println(longitud, 6);
}

void loop() {
  // Tom loop
}
```

Exempel på utskrift:

```
gps
1351824120
48.756080
2.302038
```

3. **Serialisera till en JSON-sträng**: Så här skapar du en JSON-sträng från data.

```cpp
#include <ArduinoJson.h>

void setup() {
  Serial.begin(9600);

  StaticJsonDocument<200> doc;  // Justera storleken enligt data
  doc["sensor"] = "gps";
  doc["time"] = 1351824120;
  JsonArray data = doc.createNestedArray("data");
  data.add(48.756080);
  data.add(2.302038);

  serializeJson(doc, Serial);
}

void loop() {
  // Tom loop
}
```

Exempel på utskrift (formaterad för läsbarhet):

```
{"sensor":"gps","time":1351824120,"data":[48.756080,2.302038]}
```

Att effektivt använda `ArduinoJson`-biblioteket möjliggör för Arduino-projekt att kommunicera komplexa datastrukturer i ett mänskligt läsbart format, vilket underlättar utveckling och integration med webbtjänster.
