---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:40.280168-07:00
description: "\xC5 skrive til standard feil (`stderr`) i C++ inneb\xE6rer \xE5 utgi\
  \ feilmeldinger eller diagnostikk som er adskilt fra hovedprogrammets utdata. Programmerere\u2026"
lastmod: '2024-03-13T22:44:41.116467-06:00'
model: gpt-4-0125-preview
summary: "\xC5 skrive til standard feil (`stderr`) i C++ inneb\xE6rer \xE5 utgi feilmeldinger\
  \ eller diagnostikk som er adskilt fra hovedprogrammets utdata."
title: Skriving til standardfeil
weight: 25
---

## Hvordan:
I C++ kan man skrive til standard feil ved å bruke `cerr`-strømmen, som er en del av standardbiblioteket. Her er et grunnleggende eksempel:

```cpp
#include <iostream>

int main() {
    // Skrive til standard utdata
    std::cout << "Dette er en normal melding." << std::endl;
    
    // Skrive til standard feil
    std::cerr << "Dette er en feilmelding." << std::endl;
    
    return 0;
}
```

Eksempel på utdata:
```
Dette er en normal melding.
Dette er en feilmelding.
```

I dette tilfellet vil begge meldingene vanligvis vises i terminalen din, men du kan omdirigere dem separat i et skall. For eksempel kan du sende standard utdata til en fil mens du tillater at feil vises på skjermen.

For mer avansert loggføring og feilhåndtering kan tredjepartsbiblioteker som `spdlog` eller `boost.log` benyttes. Disse bibliotekene tilbyr forbedrede funksjoner for loggføring, inkludert formatering, loggnivåer og filutdata.

Slik kan du bruke `spdlog` for å skrive en feilmelding:

```cpp
#include "spdlog/spdlog.h"

int main() {
    // Initialiser spdlog
    spdlog::info("Dette er en normal melding.");
    spdlog::error("Dette er en feilmelding.");
    
    return 0;
}
```

Merk: For å bruke `spdlog`, må du legge det til i prosjektet ditt. Dette kan du gjøre ved å klone repositoriet fra GitHub eller bruke en pakkebehandler som `vcpkg` eller `conan`.

Husk, valget mellom å direkte bruke standardstrømmer eller et bibliotek som `spdlog` avhenger av kompleksiteten i applikasjonen din og dine spesifikke behov med hensyn til feilhåndtering og loggføring.
