---
title:                "Analiza składniowa daty z łańcucha znaków"
aliases:
- /pl/arduino/parsing-a-date-from-a-string/
date:                  2024-02-03T19:13:25.882861-07:00
model:                 gpt-4-0125-preview
simple_title:         "Analiza składniowa daty z łańcucha znaków"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/arduino/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Parsowanie daty ze stringa w Arduino polega na wydobywaniu i konwertowaniu komponentów daty (rok, miesiąc, dzień) z reprezentacji tekstowej na format, który może być wykorzystany do prowadzenia ewidencji czasu, porównań lub manipulacji w szkicach. Programiści często wykonują to zadanie, aby połączyć się z komponentami takimi jak zegary czasu rzeczywistego, loggery lub aby przetworzyć dane wejściowe z interfejsów API webowych i interfejsów użytkownika, gdzie daty mogą być przedstawiane w czytelnym formacie.

## Jak to zrobić:

Bezpośrednie podejście bez biblioteki zewnętrznej:

```cpp
#include <Wire.h>
#include <RTClib.h>

void setup() {
  Serial.begin(9600);
  // Przykładowy string z datą w formacie RRRR-MM-DD
  String dateString = "2023-04-01"; 

  int year = dateString.substring(0, 4).toInt();
  int month = dateString.substring(5, 7).toInt();
  int day = dateString.substring(8, 10).toInt();

  // Inicjalizacja obiektu DateTime z przetworzonymi komponentami
  DateTime parsedDate(year, month, day);
  
  Serial.print("Przetworzona data: ");
  Serial.print(parsedDate.year(), DEC);
  Serial.print("/");
  Serial.print(parsedDate.month(), DEC);
  Serial.print("/");
  Serial.println(parsedDate.day(), DEC);
}

void loop() {}
```

Przykładowe wyjście:
```
Przetworzona data: 2023/4/1
```

Używanie biblioteki zewnętrznej (*ArduinoJson* dla bardziej skomplikowanych scenariuszy parsowania, takich jak uzyskanie daty z odpowiedzi JSON):

Najpierw zainstaluj bibliotekę ArduinoJson poprzez Menedżer Bibliotek Arduino.

```cpp
#include <ArduinoJson.h>

void setup() {
  Serial.begin(9600);

  // Symulacja odpowiedzi JSON
  String jsonResponse = "{\"date\":\"2023-07-19\"}";
  StaticJsonDocument<200> doc;
  deserializeJson(doc, jsonResponse);

  // Wydobycie stringa z datą
  const char* date = doc["date"];

  // Parsowanie daty ze stringa jak wcześniej
  int year = String(date).substring(0, 4).toInt();
  int month = String(date).substring(5, 7).toInt();
  int day = String(date).substring(8, 10).toInt();
  
  Serial.print("Przetworzona data z JSON: ");
  Serial.print(year);
  Serial.print("/");
  Serial.print(month);
  Serial.print("/");
  Serial.println(day);
}

void loop() {}
```

Przykładowe wyjście:
```
Przetworzona data z JSON: 2023/7/19
```
