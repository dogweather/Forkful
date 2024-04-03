---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:13:53.173733-07:00
description: "Komplexa tal best\xE5r av en reell del och en imagin\xE4r del, representerade\
  \ som `a + bi` d\xE4r `i` \xE4r kvadratroten av `-1`. Programmerare arbetar med\
  \ komplexa\u2026"
lastmod: '2024-03-13T22:44:38.375659-06:00'
model: gpt-4-0125-preview
summary: "Komplexa tal best\xE5r av en reell del och en imagin\xE4r del, representerade\
  \ som `a + bi` d\xE4r `i` \xE4r kvadratroten av `-1`."
title: Att arbeta med komplexa tal
weight: 14
---

## Hur man gör:
I C stöds komplexa tal av standardbiblioteket, specifikt `<complex.h>`. För att använda dem, deklarera variabler med typen `double complex` (eller `float complex` för enkel precision). Så här utför du grundläggande operationer:

```c
#include <stdio.h>
#include <complex.h>

int main() {
    double complex z1 = 1.0 + 2.0*I; // Deklarera ett komplext tal 1+2i
    double complex z2 = 1.0 - 2.0*I; // Deklarera ett annat komplext tal 1-2i
    
    // Addition
    double complex sum = z1 + z2;
    printf("Summa: %.2f + %.2fi\n", creal(sum), cimag(sum)); // Utmatning: Summa: 2.00 + 0.00i

    // Multiplikation
    double complex produkt = z1 * z2;
    printf("Produkt: %.2f + %.2fi\n", creal(produkt), cimag(produkt)); // Utmatning: Produkt: 5.00 + 0.00i

    // Komplex konjugat
    double complex konjugat = conj(z1);
    printf("Konjugat av z1: %.2f + %.2fi\n", creal(konjugat), cimag(konjugat)); // Utmatning: Konjugat av z1: 1.00 - 2.00i
    
    // Magnitud
    double magnitud = cabs(z1);
    printf("Magnitud av z1: %.2f\n", magnitud); // Utmatning: Magnitud av z1: 2.24

    // Fas
    double fas = carg(z1);
    printf("Fas av z1: %.2f\n", fas); // Utmatning i radianer
    
    return 0;
}
```
Observera att `I` är en konstant som representerar den imaginära enheten i `<complex.h>`. Funktioner som `creal()` och `cimag()` extraherar reella och imaginära delar, respektive, medan `conj()` beräknar det komplexa konjugatet. För magnitud och fas (argument) av komplexa tal används `cabs()` och `carg()`.

## Djupdykning
Stödet för komplexa tal i C är relativt nytt, standardiserat i C99. Innan detta var aritmetik med komplexa tal i C besvärlig, ofta krävdes anpassade datastrukturer och funktioner. Inkluderingen av `<complex.h>` och de komplexa datatyperna gav ett betydande lyft till språkets kapacitet för vetenskapliga och tekniska tillämpningar. Det är dock värt att notera att vissa språk, som Python, erbjuder mer intuitivt stöd för komplexa tal genom inbyggda datatyper och en rikare uppsättning biblioteksfunktioner. Trots detta är prestanda och kontroll som C erbjuder ett föredraget val för uppgifter som kräver högpresterande databehandling, även om det innebär att man måste hantera en något mer omständlig syntax för komplex aritmetik.
