---
title:                "Beregning av en dato i fremtiden eller fortiden"
date:                  2024-01-20T17:28:34.860545-07:00
model:                 gpt-4-1106-preview
html_title:           "Bash: Beregning av en dato i fremtiden eller fortiden"
simple_title:         "Beregning av en dato i fremtiden eller fortiden"
programming_language: "C++"
category:             "C++"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/cpp/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## What & Why?
Å beregne en dato i fremtiden eller fortiden betyr å finne ut nøyaktig hvilken dato det vil være etter eller før et visst tidsintervall. Programmerere gjør dette for å håndtere funksjoner relatert til tidsfrister, hendelser og planlegging i applikasjonene sine.

## How to:
Med C++20 kan vi bruke `<chrono>` biblioteket for å regne ut datoer enkelt. Her er hvordan:

```C++
#include <iostream>
#include <chrono>
#include <format>
#include <calendar>

using namespace std::chrono; // Bare for å gjøre eksemplene renere

int main() {
    // Få dagens dato ved å bruke system_clock
    auto today = std::chrono::floor<days>(system_clock::now());
    year_month_day ymd = today;
    
    // Regne ut en dato 30 dager frem i tid
    year_month_day future_date = ymd + days{30};
    
    // Regne ut en dato 30 dager i fortiden
    year_month_day past_date = ymd - days{30};

    // Vis resultatene
    std::cout << std::format("I dag: {}\n", ymd)
              << std::format("Dato 30 dager framover: {}\n", future_date)
              << std::format("Dato 30 dager tilbake: {}\n", past_date);

    return 0;
}
```

Forventet utskrift kan se slik ut:
```
I dag: 2023-04-15
Dato 30 dager framover: 2023-05-15
Dato 30 dager tilbake: 2023-03-16
```

## Deep Dive:
Før `<chrono>` biblioteket, var det mer vanlig å bruke C-funksjoner som `mktime` og `localtime` fra `<ctime>` eller egne biblioteker som Boost.Date_Time. Disse metoden var ofte mer klønete og feilutsatte.

C++20 gjorde dato- og tidsberegninger mer robust med `<chrono>`. Det gir oss typesikkerhet og forhindrer vanlige feil som å forveksle millisekunder med mikrosekunder eller å håndtere sommertid feil.

Implementasjonsdetaljer i `<chrono>` biblioteket håndterer også komplikasjoner som skuddår og kalenderendringer. Dette bidrar til at vi unngår fallgruver vi ofte støter på med manuell databehandling, og følger beste praksis med tidssoner og UTC.

## See Also:
- C++ Reference for `<chrono>`: https://en.cppreference.com/w/cpp/header/chrono
- Howard Hinnant's date library (en pådriver for funksjonalitet i C++20): https://github.com/HowardHinnant/date 
- ISO C++ Standards Committee's Calendar and Timezone proposal (P0355R7): https://wg21.link/p0355