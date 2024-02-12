---
title:                "Willekeurige getallen genereren"
aliases:
- nl/c/generating-random-numbers.md
date:                  2024-02-03T17:57:15.915325-07:00
model:                 gpt-4-0125-preview
simple_title:         "Willekeurige getallen genereren"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/c/generating-random-numbers.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Het genereren van willekeurige getallen in C houdt in dat waarden worden gecreëerd die onvoorspelbaar zijn en een specifieke verdeling volgen, zoals uniform of normaal. Deze mogelijkheid is cruciaal voor toepassingen variërend van simulaties en spellen tot cryptografische operaties, waar onvoorspelbaarheid of de simulatie van echte wereld-aleatoriek essentieel is.

## Hoe:

In C kunnen willekeurige getallen gegenereerd worden met behulp van de `rand()` functie, die deel uitmaakt van de C-standaardbibliotheek `<stdlib.h>`. Standaard produceert `rand()` pseudo-willekeurige getallen in het bereik van 0 tot `RAND_MAX` (een constante gedefinieerd in `<stdlib.h>`). Voor meer controle over het bereik, kunnen programmeurs de uitvoer van `rand()` manipuleren.

Hier is een eenvoudig voorbeeld van het genereren van een willekeurig getal tussen 0 en 99:

```c
#include <stdio.h>
#include <stdlib.h> // Voor rand() en srand()
#include <time.h>   // Voor time()

int main() {
    // Zaai de pseudo-willekeurige getallengenerator
    srand((unsigned) time(NULL));

    // Genereer een willekeurig getal tussen 0 en 99
    int randomNumber = rand() % 100;

    printf("Willekeurig Getal: %d\n", randomNumber);

    return 0;
}
```

Voorbeelduitvoer kan elke keer dat je dit programma draait variëren:

```
Willekeurig Getal: 42
```
Om willekeurige getallen binnen een ander bereik te genereren, kun je de modulo-operator (`%`) dienovereenkomstig aanpassen. Bijvoorbeeld, `rand() % 10` genereert getallen van 0 tot 9.

Het is belangrijk op te merken dat het zaaien van de pseudo-willekeurige getallengenerator (`srand()` oproep) met de huidige tijd (`time(NULL)`) zorgt voor verschillende reeksen van willekeurige getallen bij verschillende uitvoeringen van het programma. Zonder te zaaien (`srand()`), zou `rand()` elke keer dat het programma wordt uitgevoerd dezelfde reeks getallen produceren.

## Diepere Duik

De `rand()` functie en de bijbehorende zaai-functie `srand()` maken al decennia deel uit van de C-standaardbibliotheek. Ze zijn gebaseerd op algoritmen die reeksen van getallen genereren die alleen schijnbaar willekeurig zijn - vandaar de term "pseudo-willekeurig". Het onderliggende algoritme in `rand()` is meestal een lineaire congruentiegenerator (LCG).

Hoewel `rand()` en `srand()` voldoende zijn voor veel toepassingen, hebben ze bekende beperkingen, met name wat betreft de kwaliteit van de willekeurigheid en mogelijke voorspelbaarheid. Voor toepassingen die hoogwaardige willekeurigheid vereisen, zoals cryptografische operaties, moeten alternatieven zoals `/dev/random` of `/dev/urandom` (op Unix-achtige systemen), of API's aangeboden door cryptografische bibliotheken, worden overwogen.

Met de introductie van C11, heeft de ISO C-standaard een nieuwe header opgenomen, `<stdatomic.h>`, die een verfijndere controle biedt voor gelijktijdige operaties, maar niet direct betrekking heeft op willekeurigheid. Voor echte willekeurigheid in C, wenden ontwikkelaars zich vaak tot platformspecifieke of externe bibliotheken die betere algoritmen bieden of gebruikmaken van hardware-entropiebronnen.

Onthoud, hoewel `rand()` dient als een eenvoudig en toegankelijk middel om pseudo-willekeurige getallen te genereren, zijn de gebruiksmogelijkheden in moderne toepassingen beperkt door de kwaliteit en voorspelbaarheid van de uitvoer. Wanneer robuustere oplossingen nodig zijn, vooral voor veiligheidsbewuste toepassingen, wordt sterk aanbevolen om verder te kijken dan de standaardbibliotheek.
