---
title:                "Sammanslagning av strängar"
aliases:
- /sv/arduino/concatenating-strings/
date:                  2024-01-20T17:34:05.297220-07:00
model:                 gpt-4-1106-preview
simple_title:         "Sammanslagning av strängar"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/arduino/concatenating-strings.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Strängsammanslagning innebär att man kombinerar två eller flera textsträngar till en enda. Programmerare gör detta för att bygga upp meddelanden, skapa dynamiska kommandon eller samla indata i en läsbar format.

## Hur man gör:
```Arduino
String fornamn = "Anna";
String efternamn = "Svensson";
String heltNamn = fornamn + " " + efternamn; // Konkatenerar strängar med +

Serial.begin(9600);
Serial.println(heltNamn); // Skriver ut "Anna Svensson" till Serial Monitor
```
Output:
```
Anna Svensson
```

## Fördjupning
Konkatenering av strängar har varit en grundläggande del av programmering sedan de tidiga programspråken. I Arduino kan strängar sammanslås genom att använda '+'-operatören, men det finns alternativ, som `String.concat()` eller att använda char arrays och `strcat()`. Implementationen på mikrokontroller är viktig; eftersom varje operation oftast skapar en ny sträng objekt, kan det leda till fragmentering av minnet på enheter med begränsade resurser. Detta är viktigt att tänka på vid frekvent strängbearbetning.

## Se även
- [Arduino String Reference](https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/)
- [Arduino String Concatenation Operators](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/concat/)
- [Memory Management for Arduino](https://www.arduino.cc/en/Tutorial/Memory)
