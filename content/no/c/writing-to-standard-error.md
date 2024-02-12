---
title:                "Skrive til standard feil"
aliases:
- no/c/writing-to-standard-error.md
date:                  2024-02-03T18:15:07.493051-07:00
model:                 gpt-4-0125-preview
simple_title:         "Skrive til standard feil"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/c/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Å skrive til standardfeil i C innebærer å dirigere feilmeldinger og diagnostisk informasjon til en separat strøm fra hovedprogramutdataen. Programmerere gjør dette for å skille feilmeldinger fra standard utdata, noe som gjør begge deler lettere å lese og behandle separat, spesielt når man feilsøker eller logger utførelsen av programmer.

## Hvordan:

I C brukes `stderr`-strømmen til å skrive feilmeldinger. I motsetning til å skrive til standard utdata med `printf`, kan skriving til `stderr` gjøres ved hjelp av `fprintf` eller `fputs`. Slik kan du gjøre det:

```c
#include <stdio.h>

int main() {
    fprintf(stderr, "Dette er en feilmelding.\n");

    fputs("Dette er en annen feilmelding.\n", stderr);
    
    return 0;
}
```

Eksempel på utdata (til stderr):
```
Dette er en feilmelding.
Dette er en annen feilmelding.
```

Det er viktig å merke seg at selv om utdataen ser lik ut som `stdout` i konsollen, når omdirigering brukes i terminalen, blir forskjellen klar:

```sh
$ ./ditt_program > output.txt
```

Denne kommandoen omdirigerer kun standard utdata til `output.txt`, mens feilmeldingene vil fortsatt vises på skjermen.

## Dypdykk

Forskjellen mellom `stdout` og `stderr` i Unix-baserte systemer går tilbake til de tidlige dagene av C og Unix. Denne separasjonen tillater en mer robust feilhåndtering og logging, da den gjør det mulig for programmerere å omdirigere feilmeldinger uavhengig av standard programutdata. Selv om `stderr` er ubufret som standard for å sikre umiddelbar utdata av feilmeldinger, noe som hjelper i feilsøking av krasj og andre kritiske problemer, er `stdout` vanligvis bufret, noe som betyr at utdataen kan bli forsinket til bufferen er tømt (f.eks. ved programavslutning eller manuell tømming).

I moderne applikasjoner er skriving til `stderr` fortsatt relevant, spesielt for kommandolinjeverktøy og serverapplikasjoner der det er avgjørende å skille mellom vanlige loggmeldinger og feil. Imidlertid, for mer kompleks feilhåndtering, spesielt i GUI-applikasjoner eller der mer sofistikerte loggingsmekanismer er nødvendige, kan programmerere bruke dedikerte loggingbiblioteker som gir mer kontroll over meldingsformatering, destinasjoner (f.eks. filer, nettverk) og alvorlighetsnivåer (info, advarsel, feil osv.).

Selv om `stderr` gir en grunnleggende mekanisme for feilrapportering i C, betyr utviklingen av programmeringspraksiser og tilgjengeligheten av avanserte loggingsrammer at det ofte er bare utgangspunktet for moderne feilhåndteringsstrategier.
