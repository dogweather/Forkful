---
title:                "Een datum converteren naar een string"
aliases:
- /nl/cpp/converting-a-date-into-a-string/
date:                  2024-01-28T21:57:15.395587-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een datum converteren naar een string"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/cpp/converting-a-date-into-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Het omzetten van een datum naar een tekstreeks in C++ verandert een datumobject in een leesbaar tekstformaat. Het is essentieel voor het weergeven van data aan gebruikers en voor het loggen van gebeurtenissen op een mensvriendelijke manier.

## Hoe:
In modern C++ zijn de bibliotheken `<chrono>` en `<iomanip>` je vrienden voor datum-tijd operaties. Hier is een snelle methode met `std::put_time`:

```cpp
#include <iostream>
#include <iomanip>
#include <chrono>
#include <sstream>

int main() {
    auto now = std::chrono::system_clock::now(); // Huidige tijd ophalen
    auto time = std::chrono::system_clock::to_time_t(now); // Omzetten naar time_t
    
    // Omzetten naar tm struct voor opmaak
    std::tm tm = *std::localtime(&time);

    // String stream voor uitvoer
    std::stringstream ss;

    ss << std::put_time(&tm, "%Y-%m-%d %H:%M:%S"); // Formaat: JJJJ-MM-DD UU:MM:SS

    std::string date_str = ss.str(); // Omzetten naar een string

    std::cout << date_str << std::endl; // De datumstring uitvoeren
    return 0;
}
```

Voorbeelduitvoer (afhankelijk van de huidige datum en tijd):
```
2023-03-15 14:25:30
```

## Diepgaande duik
Voordat `<chrono>` in beeld kwam, moesten C++ programmeurs vaak worstelen met C-stijl tijdbeheer via `<ctime>`. Dit was minder intuïtief en meer foutgevoelig vanwege handmatig geheugenbeheer en afhankelijkheden van het platform.

Alternatieven voor `std::put_time` omvatten het gebruik van `strftime`, maar dat is meer in C-stijl. Bibliotheken van derden zoals Boost.Date_Time kunnen meer functionaliteiten bieden ten koste van het toevoegen van afhankelijkheden.

Een belangrijk implementatiedetail is het begrijpen van de formaatspecificaties in `std::put_time`, die vergelijkbaar zijn met die gebruikt in `strftime`. Je brengt placeholders in kaart naar datum- of tijdscomponenten — `%Y` voor het volledige jaar, `%m` voor de maand, enzovoort.

## Zie ook
- [`<chrono>` documentatie](https://en.cppreference.com/w/cpp/header/chrono)
- [`<iomanip>` documentatie](https://en.cppreference.com/w/cpp/header/iomanip)
- [Boost.Date_Time](https://www.boost.org/doc/libs/release/libs/date_time/)
