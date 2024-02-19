---
aliases:
- /no/arduino/interpolating-a-string/
date: 2024-01-20 17:50:04.699881-07:00
description: "Interpolering av strenger lar deg sette verdier direkte inn i en tekststreng,\
  \ noe som er hendig for \xE5 lage dynamisk tekst, som f.eks. sensorverdier eller\u2026"
lastmod: 2024-02-18 23:08:54.128065
model: gpt-4-1106-preview
summary: "Interpolering av strenger lar deg sette verdier direkte inn i en tekststreng,\
  \ noe som er hendig for \xE5 lage dynamisk tekst, som f.eks. sensorverdier eller\u2026"
title: Interpolering av en streng
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Interpolering av strenger lar deg sette verdier direkte inn i en tekststreng, noe som er hendig for å lage dynamisk tekst, som f.eks. sensorverdier eller brukerinput i meldinger. Programmerere bruker dette for å forenkle og gjøre kode mer lesbar og vedlikeholdbar.

## Slik gjør du:
```Arduino
void setup() {
  Serial.begin(9600);
}

void loop() {
  int temperatur = 22;
  Serial.print("Temperaturen er ");
  Serial.print(temperatur);
  Serial.println(" grader Celsius.");
  delay(2000); // Venter i 2 sekunder
}
```
Output: "Temperaturen er 22 grader Celsius."

## Dypdykk
Interpolering av strenger som et konsept har eksistert lenge, og finnes i mange programmeringsspråk. I Arduino C++ er det ikke en innebygd funksjon som direkte støtter strenginterpolering, i motsetning til språk som Python hvor du kan bruke f-strenger. Hos Arduino må du bruke rekkefølge av `Serial.print()` for å oppnå det samme. Når større prosjekter krever mer avansert tekstmanipulasjon, kan språkets standard `sprintf()` eller `snprintf()` funksjoner komme godt med, selv om disse kan være mer komplekse å bruke og har begrensninger på Arduino på grunn av minnestørrelse.

## Se Også
- Arduino's Serial.print() dokumentasjon: [https://www.arduino.cc/reference/en/language/functions/communication/serial/print/](https://www.arduino.cc/reference/en/language/functions/communication/serial/print/)
- en generell guide til strengmanipulering i C++: [https://www.cplusplus.com/reference/string/string/](https://www.cplusplus.com/reference/string/string/)
