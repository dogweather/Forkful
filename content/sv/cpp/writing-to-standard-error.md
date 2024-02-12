---
title:                "Skriva till standardfel"
aliases:
- sv/cpp/writing-to-standard-error.md
date:                  2024-02-03T19:32:40.595452-07:00
model:                 gpt-4-0125-preview
simple_title:         "Skriva till standardfel"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/cpp/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

Att skriva till standardfelet (`stderr`) i C++ innebär att skicka ut felmeddelanden eller diagnostik som är separata från huvudprogrammets utdata. Programmerare gör detta för att dirigera fel till en annan ström, vilket möjliggör enklare felsökning och felhantering genom att särskilja normal utdata från felmeddelanden.

## Hur man gör:

I C++ kan skrivning till standardfel uppnås genom att använda strömmen `cerr`, som är en del av standardbiblioteket. Här är ett grundläggande exempel:

```cpp
#include <iostream>

int main() {
    // Skrivning till standardutdata
    std::cout << "Detta är ett vanligt meddelande." << std::endl;
    
    // Skrivning till standardfel
    std::cerr << "Detta är ett felmeddelande." << std::endl;
    
    return 0;
}
```

Exempel på utdata:
```
Detta är ett vanligt meddelande.
Detta är ett felmeddelande.
```

I detta fall kommer båda meddelandena typiskt att visas i din terminal, men du kan omdirigera dem separat i ett skal. Till exempel kan du skicka standardutdata till en fil medan du låter fel visas på skärmen.

För mer avancerad loggning och felhantering kan tredjepartsbibliotek som `spdlog` eller `boost.log` användas. Dessa bibliotek erbjuder förbättrade funktioner för loggning, inklusive formatering, loggnivåer och filutdata.

Så här kan du använda `spdlog` för att skriva ett felmeddelande:

```cpp
#include "spdlog/spdlog.h"

int main() {
    // Initialisera spdlog
    spdlog::info("Detta är ett vanligt meddelande.");
    spdlog::error("Detta är ett felmeddelande.");
    
    return 0;
}
```

Obs: För att använda `spdlog` måste du lägga till det i ditt projekt. Du kan göra detta genom att klona repositoryt från GitHub eller använda en pakethanterare som `vcpkg` eller `conan`.

Kom ihåg att valet mellan att direkt använda standardströmmar eller ett bibliotek som `spdlog` beror på komplexiteten i din applikation och dina specifika behov med avseende på felhantering och loggning.
