---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:57:59.557022-07:00
description: "\xC5 h\xE5ndtere feil i C inneb\xE6rer \xE5 oppdage og respondere p\xE5\
  \ unormale tilstander som oppst\xE5r under kj\xF8ring av programmet. Programmerere\
  \ gj\xF8r dette for \xE5\u2026"
lastmod: '2024-03-13T22:44:41.280231-06:00'
model: gpt-4-0125-preview
summary: "\xC5 h\xE5ndtere feil i C inneb\xE6rer \xE5 oppdage og respondere p\xE5\
  \ unormale tilstander som oppst\xE5r under kj\xF8ring av programmet."
title: "H\xE5ndtering av feil"
weight: 16
---

## Hvordan:
C har ikke innebygd støtte for unntak slik som noen andre språk. I stedet støtter det seg på noen konvensjonelle feilhåndteringsstrategier, som å returnere spesielle verdier fra funksjoner og sette globale variabler som `errno`.

**Returnere spesielle verdier**

Funksjoner kan indikere feil ved å returnere en spesifikk verdi som er usannsynlig å være et gyldig resultat. Her er et eksempel med heltall:

```c
#include <stdio.h>

int inverse(int number, double *result) {
    if (number == 0) {
        return -1; // Feiltilfelle
    } else {
        *result = 1.0 / number;
        return 0; // Suksess
    }
}

int main() {
    double result;
    if (inverse(0, &result) < 0) {
        printf("Feil: Divisjon med null.\n");
    } else {
        printf("Den inverse er: %f\n", result);
    }
    
    return 0;
}
```

**Utskrift:**
```
Feil: Divisjon med null.
```

**Sjekke `errno`**

For biblioteksfunksjoner, spesielt de som samhandler med systemet eller OS (som fil-I/O), settes `errno` når en feil oppstår. For å bruke den, inkluder `errno.h` og sjekk `errno` etter en mistenkt feil:

```c
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main() {
    FILE *file = fopen("nonexistent.txt", "r");
    if (file == NULL) {
        printf("Feil ved åpning av fil: %s\n", strerror(errno));
    }
    
    return 0;
}
```

**Utskrift:**
```
Feil ved åpning av fil: No such file or directory
```

## Dypdykk
Historisk sett har C programmeringsspråkets minimalistiske design utelatt en innebygd mekanisme for unntakshåndtering, reflekterende av dets opprinnelse innen lavnivå, systemprogrammering hvor maksimal ytelse og kontroll nært opp til maskinvaren er kritisk. I stedet adopterer C en mer manuell tilnærming til feilhåndtering som passer med sin filosofi om å gi programmerere så mye kontroll som mulig, selv på bekostning av bekvemmelighet.

Selv om denne tilnærmingen stemmer godt overens med Cs designmål, kan det også føre til utførlig feilsjekkingskode og potensialet for savnede feilsjekker, som moderne språk adresserer med strukturerte unntakshåndteringsmekanismer. For eksempel tillater unntak i språk som Java eller C# for sentralisert feilprosessering, som gjør koden renere og feilhåndtering mer rett frem. Imidlertid introduserer unntak sine egne overhead og kompleksitet, som kanskje ikke er ideelt for systemnivå programering hvor C skinner.

Til tross for dens gruffhet, har denne manuelle feilhåndteringen i C informert designet av feilhåndtering i mange andre språk, og tilbyr en modell der eksplisittheten av feiltilstander kan føre til mer forutsigbar og feilsøkbar kode. For kritiske systemer, hvor feil må håndteres med nåde, sikrer Cs feilhåndteringsparadigme - kombinert med moderne beste praksiser som feilhåndteringsbiblioteker og konvensjoner - robusthet og pålitelighet.
