---
title:                "Korzystanie z debugera"
aliases:
- pl/cpp/using-a-debugger.md
date:                  2024-01-26T03:47:54.677346-07:00
model:                 gpt-4-0125-preview
simple_title:         "Korzystanie z debugera"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/cpp/using-a-debugger.md"
---

{{< edit_this_page >}}

## Co i dlaczego?
Użycie debugera oznacza uruchomienie narzędzia, które pozwala zajrzeć do wnętrza działającego programu, aby zrozumieć, co się w nim naprawdę dzieje. Programiści robią to, aby znaleźć i usunąć błędy – te irytujące problemy, które powodują, że kod zachowuje się nieoczekiwanie lub się zawiesza.

## Jak to zrobić:
C++ integruje się z debuggerami, takimi jak GDB czy debugger Visual Studio. Oto przykład użycia GDB:

```C++
#include <iostream>

int main() {
    int a = 5;
    int b = 0;
    int c = a / b; // Ojej, dzielenie przez zero!
    std::cout << c << std::endl;
    return 0;
}

// Kompilacja z:
// g++ -g -o my_program my_program.cpp

// Uruchomienie z debuggerem:
// gdb ./my_program
```

Po uruchomieniu GDB możesz ustawiać punkty przerwania, krokować przez swój kod, inspekcjonować zmienne i wiele więcej. Jeśli uruchomisz powyższy program, powinieneś zobaczyć, że Twój program się zawiesi z powodu dzielenia przez zero.

## Pogłębiona analiza
Debugowanie ma swoje korzenie we wczesnych dniach programowania, gdzie dosłownie usuwanie błędów (insektów!) z sprzętu było konieczne. Od tego czasu narzędzia do debugowania ewoluowały w skomplikowane i potężne oprogramowanie, kluczowe dla rozwoju.

Alternatywy dla GDB dla C++ to między innymi LLDB, jak również debuggery zintegrowane z IDE, takie jak te w Visual Studio, CLion czy Eclipse. Te nowoczesne środowiska zapewniają graficzne interfejsy, które czynią debugowanie mniej zastraszającym.

Szczegóły implementacji użycia debugera często zależą od Twojego środowiska programistycznego:

- Debuggery wiersza poleceń (GDB, LLDB) wymagają znajomości poleceń terminala i często wiążą się z ostrzejszą krzywą uczenia się.
- Graficzne debuggery upraszczają proces, pozwalając na interakcje typu "wskaż i kliknij" do ustawiania punktów przerwania, krokowania przez kod i obserwowania zmiennych.

Zrozumienie możliwości Twojego debugera, takich jak punkty przerwania warunkowe, punkty obserwacyjne czy ocenianie wyrażeń, może znacznie zwiększyć Twoją efektywność w diagnozowaniu problemów.

## Zobacz także
- [Dokumentacja GDB](https://www.gnu.org/software/gdb/documentation/)
- [Dokumentacja poleceń LLDB](https://lldb.llvm.org/use/map.html)
- [Samouczek debuggera Visual Studio](https://docs.microsoft.com/en-us/visualstudio/debugger/debugger-feature-tour)
- [Debugowanie z CLion](https://www.jetbrains.com/help/clion/debugging-code.html)
