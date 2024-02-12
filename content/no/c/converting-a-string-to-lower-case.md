---
title:                "Konvertering av en streng til små bokstaver"
aliases:
- no/c/converting-a-string-to-lower-case.md
date:                  2024-02-03T17:54:53.218856-07:00
model:                 gpt-4-0125-preview
simple_title:         "Konvertering av en streng til små bokstaver"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/c/converting-a-string-to-lower-case.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Å konvertere en streng til små bokstaver i C innebærer å transformere alle store bokstaver i en gitt streng til deres tilsvarende små bokstaver. Programmerere utfører ofte denne operasjonen for å standardisere tekstinnmating for sammenligning, søkeoperasjoner, eller rett og slett for estetisk konsistens i utdata.

## Hvordan:

C har ikke en innebygd funksjon for direkte konvertering av strenger til små bokstaver, i motsetning til noen høynivåspråk. Prosessen kan imidlertid enkelt implementeres ved hjelp av standardbibliotekfunksjonene i C. Nedenfor er en trinnvis veiledning og et eksempel som illustrerer hvordan du konverterer en streng til små bokstaver.

```c
#include <stdio.h>
#include <ctype.h>

void toLowerCase(char *str) {
    while (*str) {
        *str = tolower(*str);
        str++;
    }
}

int main() {
    char text[] = "Hello, World!";
    printf("Original: %s\n", text);

    toLowerCase(text);
    printf("Lowercase: %s\n", text);

    return 0;
}
```

**Eksempel på utdata:**

```
Original: Hello, World!
Lowercase: hello, world!
```

I dette eksemplet itererer `toLowerCase`-funksjonen gjennom hver karakter i inngangsstrengen, og konverterer den til sin småbokstavsekvivalent ved hjelp av `tolower`-funksjonen fra `ctype.h`. Modifiseringen utføres på stedet, og endrer den opprinnelige strengen.

## Dypdykk

`tolower`-funksjonen, som brukt i eksemplet ovenfor, er en del av C-standardsbiblioteket, spesifikt inne i `ctype.h`-headerfilen. Den opererer basert på den nåværende lokalinnstillingen, men for standard "C"-lokalinnstillingen behandler den ASCII-tegnsettet hvor 'A' til 'Z' blir konvertert til 'a' til 'z'.

Historisk sett har håndtering av tegnkoding og bokstavomforming i C vært tett koblet med ASCII-tegnsettet, noe som begrenser bruksområdet i internasjonale eller lokaliserte applikasjoner hvor tegn utenfor ASCII-settet er vanlige. Moderne programmeringsspråk kan tilby innebygde strengmetoder for å utføre bokstavomforming med tanke på lokalinnstilling og Unicode-tegn, noe C mangler medfødt.

I scenarioer som krever omfattende tekstmanipulering, spesielt med ikke-ASCII-tegn, kan programmerere vurdere å bruke biblioteker som tilbyr bedre støtte for internasjonalisering, slik som ICU (International Components for Unicode). Imidlertid, for de fleste applikasjoner som håndterer ASCII-tekst, er tilnærmingen som er demonstrert, effektiv og ukomplisert. Den fremhever Cs tilbøyelighet for å gi programmerere kontroll over datamanipulering, selv om det innebærer litt mer arbeid sammenlignet med høynivåspråk.
