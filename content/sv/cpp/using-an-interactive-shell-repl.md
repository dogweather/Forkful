---
title:                "Använda en interaktiv skal (REPL)"
aliases:
- sv/cpp/using-an-interactive-shell-repl.md
date:                  2024-01-26T04:12:00.184335-07:00
model:                 gpt-4-0125-preview
simple_title:         "Använda en interaktiv skal (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/cpp/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Vad & Varför?
En REPL (Read-Eval-Print-Loop) är en enkel, interaktiv programmeringsmiljö. Programmerare använder den för experiment med programmering i realtid, snabba uppgifter eller för att förstå nya koncept utan det arbete som krävs för att skapa fullständiga applikationer.

## Hur man gör:
C++ kommer inte med en inbyggd REPL, men verktyg som Cling erbjuder den kapaciteten. Så här använder du Cling för att beräkna summan av två tal:

```C++
#include <iostream>

int main() {
    int a = 5;
    int b = 7;
    std::cout << "Summan är: " << a + b << std::endl;
    return 0;
}

// Utdata:
// Summan är: 12
```

Starta Cling och mata in koden rad för rad och observera utdata efter varje kommando. Det ger omedelbar återkoppling, utan att behöva kompilera.

## Fördjupning
REPLs är vanliga för språk som Python eller Lisp, och de har funnits sedan 1960-talet. För C++, ett kompilerat språk, passar konceptet inte lika naturligt, vilket är varför verktyg som Cling existerar—de tolkar C++ direkt. Alternativ inkluderar online-kompilatorer eller småskaliga testprogram som kompileras på traditionellt sätt. Cling är byggt ovanpå LLVM och Clang, vilket ger en bro för att använda C++ på ett tolkat vis.

## Se också
- [Cling](https://root.cern/cling/): En interaktiv C++-tolk, byggd ovanpå LLVM och Clang-biblioteken.
- [Jupyter Notebooks](https://jupyter.org/): Erbjuder en interaktiv skal inom en notebook-miljö, stöder C++ genom xeus-cling-kärnan.
- [LLVM](https://llvm.org/): En samling modulära och återanvändbara kompilator- och verktygskedjeteknologier, som Cling bygger på.
