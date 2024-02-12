---
title:                "Analysera ett datum från en sträng"
date:                  2024-02-03T19:13:26.613644-07:00
model:                 gpt-4-0125-preview
simple_title:         "Analysera ett datum från en sträng"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/arduino/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

Att tolka ett datum från en sträng i Arduino innebär att extrahera och konvertera datumkomponenterna (år, månad, dag) från en textuell representation till ett format som kan användas för tidsuppföljning, jämförelser eller manipulationer inom sketcher. Programmerare utför ofta denna uppgift för att interagera med komponenter som realtidsklockor, loggar, eller för att bearbeta indata från webb-API:er och användargränssnitt där datum kan presenteras i ett läsbart format.

## Hur man gör:

Direkt metod utan tredjepartsbibliotek:

```cpp
#include <Wire.h>
#include <RTClib.h>

void setup() {
  Serial.begin(9600);
  // Exempel på datumsträng i YYYY-MM-DD-format
  String dateString = "2023-04-01"; 

  int year = dateString.substring(0, 4).toInt();
  int month = dateString.substring(5, 7).toInt();
  int day = dateString.substring(8, 10).toInt();

  // Initiera ett DateTime-objekt med tolkade komponenter
  DateTime parsedDate(year, month, day);
  
  Serial.print("Tolkat Datum: ");
  Serial.print(parsedDate.year(), DEC);
  Serial.print("/");
  Serial.print(parsedDate.month(), DEC);
  Serial.print("/");
  Serial.println(parsedDate.day(), DEC);
}

void loop() {}
```

Exempel på utdata:
```
Tolkat Datum: 2023/4/1
```

Använda ett tredjepartsbibliotek (*ArduinoJson* för mer komplexa tolkningsscenarier, som att hämta ett datum från ett JSON-svar):

Först, installera ArduinoJson-biblioteket genom Arduino Library Manager.

```cpp
#include <ArduinoJson.h>

void setup() {
  Serial.begin(9600);

  // Simulera ett JSON-svar
  String jsonResponse = "{\"date\":\"2023-07-19\"}";
  StaticJsonDocument<200> doc;
  deserializeJson(doc, jsonResponse);

  // Extrahera datumsträngen
  const char* date = doc["date"];

  // Tolkar datumet från strängen som tidigare
  int year = String(date).substring(0, 4).toInt();
  int month = String(date).substring(5, 7).toInt();
  int day = String(date).substring(8, 10).toInt();
  
  Serial.print("Tolkat Datum från JSON: ");
  Serial.print(year);
  Serial.print("/");
  Serial.print(month);
  Serial.print("/");
  Serial.println(day);
}

void loop() {}
```

Exempel på utdata:
```
Tolkat Datum från JSON: 2023/7/19
```
