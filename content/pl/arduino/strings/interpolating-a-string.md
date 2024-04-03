---
date: 2024-01-20 17:50:08.130580-07:00
description: "Interpolacja ci\u0105gu znak\xF3w umo\u017Cliwia wstawianie zmiennych\
  \ bezpo\u015Brednio w tekst. U\u017Cywamy jej, by u\u0142atwi\u0107 tworzenie dynamicznych\
  \ wiadomo\u015Bci i formatowa\u0107 je\u2026"
lastmod: '2024-03-13T22:44:35.658487-06:00'
model: gpt-4-1106-preview
summary: "Interpolacja ci\u0105gu znak\xF3w umo\u017Cliwia wstawianie zmiennych bezpo\u015B\
  rednio w tekst."
title: "Interpolacja \u0142a\u0144cuch\xF3w znak\xF3w"
weight: 8
---

## How to: (Jak to zrobić:)
Arduino nie ma natywnej funkcji interpolacji ciągów, ale możemy osiągnąć podobny efekt używając `sprintf` lub łącząc ciągi przy użyciu operatora `+`.

```Arduino
char buffer[50];
int temperature = 23;

void setup() {
  Serial.begin(9600);
  
  // Użycie sprintf do wstawienia zmiennej do ciągu
  sprintf(buffer, "Temperatura to: %d stopni Celsjusza.", temperature);
  Serial.println(buffer);

  // Alternatywne łączenie ciągów
  String message = "Temperatura to: " + String(temperature) + " stopni Celsjusza.";
  Serial.println(message);
}

void loop() {
  // Nic nie robimy w pętli.
}
```
Wyjście jest takie samo dla obu metod:
```
Temperatura to: 23 stopni Celsjusza.
```

## Deep Dive (Dogłębna analiza)
Choć Arduino nie posiada wbudowanej funkcji interpolacji ciągów jak w językach wyższego poziomu (np. Python), 'sprintf' jest wszechstronnym narzędziem służącym do formatowania ciągów. Po raz pierwszy pojawiło się w języku C i jest często używane w systemach wbudowanych dla zarządzania pamięcią. Alternatywnie, możemy łączyć ciągi za pomocą `+`, ale jest to mniej wydajne pamięciowo. Implementacja `sprintf` na platformach Arduino nie obsługuje zmiennych typu `float` domyślnie, więc dla wartości zmiennoprzecinkowych trzeba korzystać z `dtostrf`.

## See Also (Zobacz również)
- [Dokumentacja Arduino - String Object](https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/)
- [Tutorial: Managing Memory](https://learn.adafruit.com/memories-of-an-arduino)
