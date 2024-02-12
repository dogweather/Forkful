---
title:                "Korzystanie z interaktywnego shella (REPL)"
date:                  2024-01-26T04:12:11.188552-07:00
model:                 gpt-4-0125-preview
simple_title:         "Korzystanie z interaktywnego shella (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/cpp/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Co i dlaczego?
REPL (Read-Eval-Print-Loop, pętla czytaj-wykonuj-wypisz) to proste środowisko programistyczne interaktywne. Programiści używają go do eksperymentowania z językiem w czasie rzeczywistym, szybkich zadań, lub do zrozumienia nowych koncepcji bez konieczności tworzenia pełnoprawnych aplikacji.

## Jak to zrobić:
C++ nie posiada wbudowanego REPL, ale narzędzia takie jak Cling oferują tę możliwość. Oto jak używać Clinga do obliczenia sumy dwóch liczb:

```C++
#include <iostream>

int main() {
    int a = 5;
    int b = 7;
    std::cout << "Suma wynosi: " << a + b << std::endl;
    return 0;
}

// Wynik:
// Suma wynosi: 12
```

Uruchom Clinga i wprowadzaj kod linia po linii, obserwując wynik po każdym poleceniu. To natychmiastowa informacja zwrotna, bez kompilacji.

## Dogłębna analiza
REPL są powszechne dla języków takich jak Python czy Lisp i istnieją od lat 60. Dla C++, języka kompilowanego, koncepcja ta nie pasuje tak naturalnie, dlatego istnieją narzędzia takie jak Cling — interpretują C++ na bieżąco. Alternatywami są kompilatory online lub małe programy testowe kompilowane tradycyjnie. Cling jest zbudowany na bazie LLVM i Clanga, zapewniając most dla C++, aby można było go używać w sposób interpretowany.

## Zobacz też
- [Cling](https://root.cern/cling/): Interaktywny interpreter C++, zbudowany na bazie bibliotek LLVM i Clang.
- [Notatniki Jupytera](https://jupyter.org/): Oferują interaktywną powłokę w środowisku notatnika, obsługują C++ poprzez jądro xeus-cling.
- [LLVM](https://llvm.org/): Zbiór modułowych i wielokrotnego użytku technologii kompilatora i narzędzi, na których Cling się opiera.
