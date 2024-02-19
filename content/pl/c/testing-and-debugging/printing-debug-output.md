---
aliases:
- /pl/c/printing-debug-output/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:05:19.134146-07:00
description: "Drukowanie danych diagnostycznych polega na generowaniu tymczasowych,\
  \ informacyjnych komunikat\xF3w logowania, kt\xF3re mog\u0105 pom\xF3c programistom\
  \ zrozumie\u0107\u2026"
lastmod: 2024-02-18 23:08:50.082896
model: gpt-4-0125-preview
summary: "Drukowanie danych diagnostycznych polega na generowaniu tymczasowych, informacyjnych\
  \ komunikat\xF3w logowania, kt\xF3re mog\u0105 pom\xF3c programistom zrozumie\u0107\
  \u2026"
title: "Drukowanie komunikat\xF3w debugowania"
---

{{< edit_this_page >}}

## Co i dlaczego?

Drukowanie danych diagnostycznych polega na generowaniu tymczasowych, informacyjnych komunikatów logowania, które mogą pomóc programistom zrozumieć przepływ i stan programu podczas jego wykonywania. Programiści robią to, aby zidentyfikować i zdiagnozować błędy oprogramowania lub nieoczekiwane zachowanie w logice programu.

## Jak to zrobić:

W C najczęstszym sposobem drukowania danych diagnostycznych jest użycie funkcji `printf` z biblioteki standardowej wejścia/wyjścia. Funkcja `printf` pozwala na sformatowane wyjście na standardowe urządzenie wyjściowe, zazwyczaj ekran. Oto prosty przykład:

```c
#include <stdio.h>

int main() {
    int x = 5;
    printf("Diagnostyka: Wartość x wynosi %d\n", x);
    
    // Logika twojego programu tutaj
    
    return 0;
}
```

Przykładowe wyjście:

```
Diagnostyka: Wartość x wynosi 5
```

Dla bardziej zaawansowanego druku diagnostycznego możesz chcieć dołączyć informacje o nazwie pliku i numerze linii. Można to zrobić za pomocą predefiniowanych makr `__FILE__` i `__LINE__` w taki sposób:

```c
#define DEBUG_PRINT(fmt, args...) fprintf(stderr, "DEBUGOWANIE: %s:%d: " fmt, __FILE__, __LINE__, ##args)

int main() {
    int testowaWartość = 10;
    DEBUG_PRINT("Testowa wartość wynosi %d\n", testowaWartość);
    
    // Logika twojego programu tutaj
    
    return 0;
}
```

Przykładowe wyjście:

```
DEBUGOWANIE: example.c:6: Testowa wartość wynosi 10
```

Zwróć uwagę, że w tym przykładzie używamy `fprintf` do wyjścia na standardowy strumień błędów (`stderr`), co jest często bardziej odpowiednie dla komunikatów diagnostycznych.

## Dogłębnie

Historycznie techniki debugowania w C były ręczne i podstawowe, ze względu na filozofię bliskości do sprzętu i wiek języka. Podczas gdy nowoczesne języki mogą obejmować zaawansowane, wbudowane biblioteki debugowania lub polegać mocno na funkcjach Zintegrowanego Środowiska Programistycznego (IDE), programiści C często polegają na ręcznym wstawianiu instrukcji drukowania, takich jak te pokazane powyżej, aby śledzić wykonanie swojego programu.

Jedną rzeczą, na którą należy uważać przy drukowaniu danych diagnostycznych, jest ich potencjał do zaśmiecania wyjścia i prowadzenia do problemów z wydajnością, szczególnie jeśli zostaną nieumyślnie pozostawione w kodzie produkcyjnym. Z tych powodów, użycie kompilacji warunkowej (np. `#ifdef DEBUG ... #endif`) może być lepszym podejściem, pozwalającym na dołączanie lub wykluczanie instrukcji diagnostycznych na podstawie flag kompilacji.

Ponadto, dostępne są teraz bardziej zaawansowane narzędzia i biblioteki do debugowania w C, takie jak GDB (GNU Debugger) i Valgrind do wykrywania wycieków pamięci. Te narzędzia oferują bardziej zintegrowane podejście do debugowania, bez potrzeby modyfikacji kodu przez wstawianie instrukcji drukowania.

Mimo to, prostota i natychmiastowy feedback debugowania za pomocą `printf` nie może być niedoceniona, czyniąc go użytecznym narzędziem w arsenale programisty, szczególnie dla tych, którzy dopiero uczą się subtelności C.
