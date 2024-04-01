---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:09:59.651462-07:00
description: "Debuggery w j\u0119zyku C to specjalistyczne narz\u0119dzia, kt\xF3\
  re pozwalaj\u0105 programistom krok po kroku przegl\u0105da\u0107 sw\xF3j kod, inspekcjonowa\u0107\
  \ zmienne i monitorowa\u0107\u2026"
lastmod: '2024-03-13T22:44:35.891468-06:00'
model: gpt-4-0125-preview
summary: "Debuggery w j\u0119zyku C to specjalistyczne narz\u0119dzia, kt\xF3re pozwalaj\u0105\
  \ programistom krok po kroku przegl\u0105da\u0107 sw\xF3j kod, inspekcjonowa\u0107\
  \ zmienne i monitorowa\u0107\u2026"
title: Korzystanie z debugera
---

## Jak to zrobić:
GDB (GNU Debugger) jest najczęściej używanym debugerem dla programowania w języku C. Oto krótki przewodnik, jak używać GDB do debugowania prostego programu w C.

Najpierw skompiluj swój program w C z flagą `-g`, aby dołączyć informacje debugowania:

```c
gcc -g program.c -o program
```

Następnie uruchom GDB ze skompilowanym programem:

```bash
gdb ./program
```

Teraz możesz użyć różnych poleceń w GDB, aby kontrolować jego działanie. Oto kilka podstawowych poleceń:

- `break`: Ustaw punkt przerwania w określonej linii lub funkcji, aby zatrzymać wykonanie.
  - Przykład: `break 10` lub `break main`
- `run`: Rozpocznij wykonanie programu w GDB.
- `next`: Wykonaj następną linię kodu, nie wchodząc do funkcji.
- `step`: Wykonaj następną linię kodu, wchodząc do funkcji.
- `print`: Wyświetl wartość zmiennej.
- `continue`: Wznów wykonanie do następnego punktu przerwania.
- `quit`: Wyjdź z GDB.

Oto przykład sesji debugowania prostego programu:

```c
#include <stdio.h>

int main() {
    int i;
    for (i = 0; i < 5; i++) {
        printf("%d\n", i);
    }
    return 0;
}
```

Skompiluj i uruchom GDB, jak opisano. Ustaw punkt przerwania przy linii `printf` używając `break 5`, a następnie `run`. Użyj `next`, aby krok po kroku przejść przez pętlę i `print i`, aby zbadać zmienną pętli.

Przykładowy wynik po ustawieniu punktu przerwania i przed pierwszą iteracją:

```
Breakpoint 1, main () at program.c:5
5         printf("%d\n", i);
```

Używanie `print i` po kilku iteracjach:

```
$3 = 2
```

To demonstruje badanie stanu i przepływu prostego programu.

## Wgłębianie się
Koncepcja debugowania znacznie ewoluowała od wczesnych dni programowania, gdzie fizyczne błędy (dosłowne owady) mogły powodować problemy w mechanicznych komputerach. Dzisiaj debuggery takie jak GDB oferują zaawansowane funkcje wykraczające poza podstawowe kroki i inspekcje zmiennych, takie jak debugowanie wsteczne (wykonywanie programu do tyłu), warunkowe punkty przerwania i skrypty do automatycznych zadań debugowania.

Chociaż GDB jest potężny i szeroko używany, może być gęsty i trudny dla początkujących. Alternatywne narzędzia do debugowania i środowiska zintegrowane (IDE) takie jak Visual Studio Code, CLion lub Eclipse oferują bardziej przyjazne dla użytkownika interfejsy do debugowania kodu C, często integrując wizualne pomoce i bardziej intuicyjne kontrole. Te alternatywy mogą nie oferować pełnej głębi funkcjonalności GDB, ale mogą być bardziej dostępne dla nowicjuszy w programowaniu w języku C.

Ponadto, pojawienie się protokołów serwera językowego i standardów debugowania ułatwiło rozwiązania do debugowania międzyplatformowego, czyniąc doświadczenie debugowania bardziej spójnym w różnych narzędziach i środowiskach. Pomimo tych postępów, nauka detali tradycyjnego debugera jak GDB dostarcza cennych wglądów w wykonanie programów w języku C i pozostaje kluczową umiejętnością w zestawie narzędzi programisty.
