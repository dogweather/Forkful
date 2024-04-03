---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:00:05.246922-07:00
description: "Att tolka ett datum fr\xE5n en str\xE4ng i C inneb\xE4r att konvertera\
  \ textuella representationer av datum till ett format som program kan manipulera\
  \ och analysera\u2026"
lastmod: '2024-03-13T22:44:38.392740-06:00'
model: gpt-4-0125-preview
summary: "Att tolka ett datum fr\xE5n en str\xE4ng i C inneb\xE4r att konvertera textuella\
  \ representationer av datum till ett format som program kan manipulera och analysera\
  \ mer effektivt."
title: "Omtolkning av ett datum fr\xE5n en str\xE4ng"
weight: 30
---

## Hur man gör:
C erbjuder inte ett inbyggt sätt att tolka datum från strängar direkt, så vi använder ofta funktionen `strptime` som finns i biblioteket `<time.h>` för POSIX-system. Denna funktion gör det möjligt för oss att specificera det förväntade formatet på inmatningssträngen och tolka den till en `struct tm`, som representerar kalenderdatum och tid uppdelat i dess komponenter.

Här är ett enkelt exempel på hur man använder `strptime` för att tolka ett datum från en sträng:

```c
#include <time.h>
#include <stdio.h>

int main() {
    const char *dateStr = "2023-04-01";
    struct tm tm;
    char buf[255];

    // Tolkar datumsträngen till struct tm
    if (strptime(dateStr, "%Y-%m-%d", &tm) == NULL) {
        printf("Misslyckades med att tolka datum.\n");
    } else {
        // Använder strftime för att skriva ut datumet i ett läsbart format
        strftime(buf, sizeof(buf), "%A, %B %d, %Y", &tm);
        printf("Tolkat datum: %s\n", buf);
    }

    return 0;
}
```

Exempelutskrift för detta program skulle vara:

```
Tolkat datum: lördag, april 01, 2023
```

Det är väsentligt att hantera potentiella fel, såsom att `strptime` inte lyckas matcha mönstret eller stöter på oväntad inmatning.

## Fördjupning
Funktionen `strptime`, även om den är kraftfull, är inte en del av det standardiserade C-biblioteket och finns främst på POSIX-kompatibla system såsom Linux och UNIX. Denna begränsning innebär att program som förlitar sig på `strptime` för att tolka datum från strängar kanske inte är portabla till icke-POSIX-system som Windows utan ytterligare kompatibilitetslager eller bibliotek.

Historiskt sett krävde hantering av datum och tider i C mycket manuell manipulation och omsorg, särskilt med tanke på olika lokala inställningar och tidszoner. Moderna alternativ och tillägg till C, som C++ `<chrono>`-biblioteket och tredjepartsbibliotek som Howard Hinnants datumlibrary för C++, erbjuder mer robusta lösningar för datum- och tidmanipulering, inklusive tolkning. Dessa bibliotek tillhandahåller vanligtvis bättre stöd för ett brett utbud av datumformat, tidszoner och felhanteringsmekanismer, vilket gör dem föredragna för nya projekt som kräver omfattande datum- och tidmanipuleringsförmåga.

Ändå kan förståelsen av hur man tolkar datum från strängar i C vara fördelaktig, särskilt när man arbetar med eller underhåller projekt som behöver vara kompatibla med system där dessa moderna verktyg inte finns tillgängliga eller när man arbetar inom begränsningarna av strikta C-programmeringsmiljöer.
