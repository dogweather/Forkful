---
date: 2024-01-26 00:59:29.046283-07:00
description: "\"Logowanie\" to tworzenie zapisu wydarze\u0144, transakcji lub dzia\u0142\
  a\u0144, kt\xF3re maj\u0105 miejsce w czasie w systemie. Programi\u015Bci u\u017C\
  ywaj\u0105 go do debugowania,\u2026"
lastmod: '2024-03-13T22:44:35.677800-06:00'
model: gpt-4-1106-preview
summary: "\"Logowanie\" to tworzenie zapisu wydarze\u0144, transakcji lub dzia\u0142\
  a\u0144, kt\xF3re maj\u0105 miejsce w czasie w systemie."
title: "Rejestrowanie zdarze\u0144"
weight: 17
---

## Jak to zrobić:
Arduino nie posiada wbudowanej biblioteki do logowania, tak jak niektóre inne środowiska, ale można zaimplementować podstawowe logowanie do konsoli szeregowej bez większego problemu. Oto krótki przykład, który pomoże Ci zacząć:

```arduino
void setup() {
  // Rozpocznij komunikację szeregową z podaną szybkością transmisji
  Serial.begin(9600);

  // Czekaj na połączenie z portem szeregowym - tylko konieczne w niektórych płytach
  while (!Serial) {
    ; // czekaj na połączenie z portem szeregowym. Konieczne dla natywnego USB
  }

  // Zaloguj informacyjną wiadomość wskazującą, że proces konfiguracji jest zakończony
  Serial.println("Konfiguracja zakończona!");
}

void loop() {
  // Prosty logger, który wyświetla czas pracy co sekundę
  static unsigned long lastLogTime = 0;
  unsigned long currentMillis = millis();

  if (currentMillis - lastLogTime >= 1000) {
    lastLogTime = currentMillis;
    Serial.print("Czas pracy (ms): ");
    Serial.println(currentMillis);

    // Tutaj możesz również dodać logi błędów, ostrzeżenia lub inne informacje.
  }
  
  // Reszta logiki programu tutaj...
}
```

Przykładowe wyjście Serialne:
```
Konfiguracja zakończona!
Czas pracy (ms): 1000
Czas pracy (ms): 2000
Czas pracy (ms): 3000
...
```

## Szczegółowa analiza:
Historycznie rzecz biorąc, logowanie na mikrokontrolerach nie było tak proste jak w pełnoprawnym systemie operacyjnym. Ograniczone zasoby oznaczały, że każdy bajt się liczył i programiści musieli uważać, aby nie zatkać systemu. Z rozwojem bardziej zaawansowanych płyt i platformy Arduino ułatwiającej proces, logowanie stało się bardziej dostępne.

Chociaż powyższy kod demonstrowany jest poprzez interfejs szeregowy, inne metody obejmują zapis na kartę SD, wysyłanie danych poprzez sieć na zdalny serwer, czy nawet wyświetlanie na małym wyświetlaczu LCD.

Implementacja systemu logowania wiąże się z rozważeniami, takimi jak rotacja, poziom ważności (info, debug, ostrzeżenie, błąd) oraz wpływ na wydajność. Na Arduino może być konieczna ostrożność dotycząca ograniczeń pamięciowych przy logowaniu skomplikowanych struktur danych. W przypadku zdalnego logowania, ważne jest również zabezpieczenie przesyłanych logów.

Istnieją bardziej zaawansowane rozwiązania, takie jak Syslog, szeroko przyjęty standard logowania, który istnieje poza światem Arduino, ale można zintegrować biblioteki stron trzecich, które oferują podobną funkcjonalność z różnymi stopniami złożoności i wymagań dotyczących zasobów.

## Zobacz również:
- [Referencja `Serial` Arduino](https://www.arduino.cc/reference/en/language/functions/communication/serial/)
- [Logowanie na karcie SD z Arduino](https://www.arduino.cc/en/Tutorial/LibraryExamples/Datalogger)
- [Tarcza do logowania danych SparkFun](https://www.sparkfun.com/products/13712)
- [TinyWeb: Praktyczny przykład zdalnego logowania z Arduino](https://www.arduino.cc/en/Tutorial/WebClientRepeating)
