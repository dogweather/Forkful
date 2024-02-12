---
title:                "Praca z liczbami zespolonymi"
aliases:
- pl/arduino/working-with-complex-numbers.md
date:                  2024-01-26T04:36:53.136927-07:00
model:                 gpt-4-0125-preview
simple_title:         "Praca z liczbami zespolonymi"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/arduino/working-with-complex-numbers.md"
---

{{< edit_this_page >}}

## Co i dlaczego?
Liczby zespolone mają część rzeczywistą i część urojoną, zwykle zapisywane jako `a + bi`. Są one niezbędne w niektórych projektach Arduino, które wymagają zaawansowanych obliczeń matematycznych, takich jak przetwarzanie sygnałów, inżynieria elektryczna czy jakakolwiek inna dziedzina, gdzie zjawiska najlepiej jest modelować na płaszczyźnie.

## Jak to zrobić:
```Arduino
#include <Complex.h>

void setup() {
  Serial.begin(9600); // Rozpoczęcie komunikacji szeregowej
  
  Complex myComplex(2, 3); // Tworzenie liczby zespolonej 2 + 3i
  Complex anotherComplex(1, 1); // Tworzenie kolejnej liczby zespolonej 1 + 1i
  
  // Dodawanie
  Complex result = myComplex + anotherComplex; 
  Serial.print("Dodawanie: "); 
  result.print(); // Wypisuje 3 + 4i
  
  // Mnożenie
  result = myComplex * anotherComplex; 
  Serial.print("Mnożenie: ");
  result.print(); // Wypisuje -1 + 5i
}

void loop() {
  // Nie używane w tym przykładzie
}
```
Przykładowe wyjście:
```
Dodawanie: 3 + 4i
Mnożenie: -1 + 5i
```

## Szczegółowe omówienie
Początkowo liczby zespolone były przyjmowane ze sceptycyzmem, ale stały się one centralną częścią różnych dziedzin naukowych. Historycznie, zostały uznane za dostarczające rozwiązania równań wielomianowych, które nie mają rozwiązań rzeczywistych.

Arduino nie zawiera liczb zespolonych w swojej standardowej bibliotece, ale można wykorzystać biblioteki takie jak `Complex.h` do ich obsługi. Wewnętrznie, te biblioteki definiują klasę Complex, zwykle używając dwóch liczb typu double do przechowywania części rzeczywistej i urojonej, oraz przeciążają operatory, aby obsługiwać arytmetykę.

Jako alternatywę, dla aplikacji, które nie wymagają w sposób inherentny arytmetyki liczb zespolonych, można rozważyć użycie innych strategii matematycznych lub bibliotek. Pamiętaj jednak, że użycie liczb typu float zamiast liczb zespolonych może nadmiernie upraszczać niektóre problemy.

## Zobacz również
- Bibliotekę [Complex.h](https://github.com/RobTillaart/Complex) autorstwa Roba Tillaarta.
- Głębsze wprowadzenie do [matematyki za liczbami zespolonymi](https://mathworld.wolfram.com/ComplexNumber.html).
