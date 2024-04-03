---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:57:23.451971-07:00
description: "Pobieranie bie\u017C\u0105cej daty w j\u0119zyku C wi\u0105\u017Ce si\u0119\
  \ z wykorzystaniem standardowej biblioteki C do pobrania i sformatowania bie\u017C\
  \u0105cej daty i czasu systemu.\u2026"
lastmod: '2024-03-13T22:44:35.897833-06:00'
model: gpt-4-0125-preview
summary: "Pobieranie bie\u017C\u0105cej daty w j\u0119zyku C wi\u0105\u017Ce si\u0119\
  \ z wykorzystaniem standardowej biblioteki C do pobrania i sformatowania bie\u017C\
  \u0105cej daty i czasu systemu."
title: "Pobieranie bie\u017C\u0105cej daty"
weight: 29
---

## Jak to zrobić:
W C, nagłówek `<time.h>` zapewnia niezbędne funkcje i typy do pracy z datami i czasem. Funkcja `time()` pobiera bieżący czas, podczas gdy `localtime()` konwertuje ten czas na strefę czasową lokalną. Aby wyświetlić datę, używamy `strftime()`, aby sformatować ją jako ciąg znaków.

Oto podstawowy przykład:

```c
#include <stdio.h>
#include <time.h>

int main() {
    char buffer[80];
    time_t rawtime;
    struct tm *timeinfo;

    // Pobranie bieżącego czasu
    time(&rawtime);
    // Konwersja na czas lokalny
    timeinfo = localtime(&rawtime);
    
    // Formatowanie daty i wyświetlanie jej
    strftime(buffer, 80, "Dzisiejsza data to %Y-%m-%d", timeinfo);
    printf("%s\n", buffer);

    return 0;
}
```

Przykładowe wyjście może wyglądać tak:

```
Dzisiejsza data to 2023-04-12
```

## Zagłębienie się
Obsługa czasu w C, ułatwiona przez `<time.h>`, nawiązuje do najwcześniejszych dni języka i systemów UNIX. Opiera się na typie danych `time_t`, który reprezentuje bieżący czas jako liczbę sekund od ery Unix (1 stycznia 1970). Chociaż jest to efektywne i uniwersalnie kompatybilne, oznacza to również, że funkcje czasu standardowej biblioteki C są z natury ograniczone przez zakres i rozdzielczość `time_t`.

Współczesne aplikacje, szczególnie te wymagające precyzyjnych znaczników czasowych lub mające do czynienia z datami daleko w przyszłości lub przeszłości, mogą uznać te ograniczenia za wyzwanie. Na przykład, problem roku 2038 jest znaną ilustracją, gdzie systemy używające 32-bitowego `time_t` będą miały przepełnienie.

Dla bardziej złożonej obsługi czasu i daty, wielu programistów zwraca się do zewnętrznych bibliotek lub funkcjonalności dostarczonych przez system operacyjny. Na przykład, w C++, biblioteka `<chrono>` oferuje bardziej precyzyjne i wszechstronne możliwości manipulacji czasem.

Pomimo swoich ograniczeń, prostota i wszechobecność funkcji czasowych C sprawiają, że są one doskonale odpowiednie dla wielu aplikacji. Zrozumienie tych narzędzi jest fundamentalne dla programistów C, oferując mieszankę historycznego kontekstu programowania i praktycznej, codziennej użyteczności.
