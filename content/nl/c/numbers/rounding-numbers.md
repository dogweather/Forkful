---
aliases:
- /nl/c/rounding-numbers/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:07:38.470018-07:00
description: "Getallen afronden is het proces waarbij de cijfers van een nummer worden\
  \ aangepast om de precisie volgens bepaalde regels te verminderen, hetzij naar het\u2026"
lastmod: 2024-02-18 23:09:02.366955
model: gpt-4-0125-preview
summary: "Getallen afronden is het proces waarbij de cijfers van een nummer worden\
  \ aangepast om de precisie volgens bepaalde regels te verminderen, hetzij naar het\u2026"
title: Afronden van getallen
---

{{< edit_this_page >}}

## Wat & Waarom?

Getallen afronden is het proces waarbij de cijfers van een nummer worden aangepast om de precisie volgens bepaalde regels te verminderen, hetzij naar het dichtstbijzijnde hele getal of een gespecificeerd aantal decimalen. Programmeurs doen dit om redenen variërend van het beperken van de hoeveelheid opslag die nodig is, tot het vereenvoudigen van de uitvoer voor consumptie door de gebruiker, of het verzekeren van nauwkeurige wiskundige bewerkingen die gevoelig zijn voor zeer kleine varianties.

## Hoe:

Getallen afronden in C kan worden bereikt met behulp van verschillende functies, maar de meest voorkomende benadering omvat de `floor()`, `ceil()`, en `round()` functies. Deze functies maken deel uit van de standaard wiskunde-bibliotheek, dus je moet `math.h` in je programma opnemen.

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 9.527;

    // Met floor() naar beneden afronden
    double floorResult = floor(num);
    printf("floor(9.527) = %.0f\n", floorResult);

    // Met ceil() naar boven afronden
    double ceilResult = ceil(num);
    printf("ceil(9.527) = %.0f\n", ceilResult);

    // Met round() naar het dichtstbijzijnde gehele getal afronden
    double roundResult = round(num);
    printf("round(9.527) = %.0f\n", roundResult);

    // Afronden op een gespecificeerd aantal decimalen involves vermenigvuldiging en deling
    double twoDecimalPlaces = round(num * 100) / 100;
    printf("Afronden op twee decimalen: %.2f\n", twoDecimalPlaces);

    return 0;
}
```

Uitvoer:
```
floor(9.527) = 9
ceil(9.527) = 10
round(9.527) = 10
Afronden op twee decimalen: 9.53
```

## Diepgaande Duik

Getallen afronden heeft diepe historische wortels in wiskunde en berekeningen, essentieel voor zowel theoretische als toegepaste aspecten. In C, hoewel `floor()`, `ceil()`, en `round()` basisfunctionaliteit bieden, is de essentie van het afronden van floats naar gehele getallen of specifieke decimalen genuanceerder vanwege de binaire representatie van zwevende-kommagetallen. Deze representatie kan leiden tot onverwachte resultaten vanwege hoe getallen die niet precies in binair kunnen worden gerepresenteerd (zoals 0.1) worden behandeld.

Deze functies maken deel uit van de C-standaardbibliotheek, gedefinieerd in `<math.h>`. Bij het afronden van getallen, vooral voor financiële of precieze technische berekeningen, moet men de implicaties van het gebruik van binaire zwevende-kommagetallen overwegen. Alternatieven voor de ingebouwde C-functies voor zeer nauwkeurige of specifiek decimale afronding kunnen het implementeren van aangepaste afrondingsfuncties of het gebruik van bibliotheken voor willekeurige-precisie rekenkunde, zoals GMP of MPFR, omvatten, hoewel deze extra complexiteit en afhankelijkheden introduceren.

In de praktijk, de juiste benadering kiezen voor afronden in C betekent een evenwicht vinden tussen de behoefte aan precisie, prestatie en praktische bruikbaarheid, met een scherp begrip van de domeinspecifieke vereisten van de applicatie die wordt ontwikkeld.
