---
aliases:
- /nl/bash/comparing-two-dates/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:56:18.686248-07:00
description: "Het vergelijken van twee datums stelt je in staat om uit te zoeken welke\
  \ earlier, later is, of als ze op hetzelfde moment plaatsvinden. Programmeurs doen\u2026"
lastmod: 2024-02-18 23:09:02.055037
model: gpt-4-0125-preview
summary: "Het vergelijken van twee datums stelt je in staat om uit te zoeken welke\
  \ earlier, later is, of als ze op hetzelfde moment plaatsvinden. Programmeurs doen\u2026"
title: Twee datums vergelijken
---

{{< edit_this_page >}}

## Wat & Waarom?
Het vergelijken van twee datums stelt je in staat om uit te zoeken welke earlier, later is, of als ze op hetzelfde moment plaatsvinden. Programmeurs doen dit om gebeurtenissen te sorteren, getimede acties te activeren, of gewoon om verstreken tijd bij te houden.

## Hoe te:
Hier is een snelle manier om twee datums in Bash te vergelijken:

```Bash
date1="2023-04-01"
date2="2023-04-15"

# Converteer datums naar seconden sinds het tijdperk
sec1=$(date -d "$date1" +%s)
sec2=$(date -d "$date2" +%s)

# Vergelijk de datums
if [ $sec1 -eq $sec2 ]; then
    echo "Datums zijn hetzelfde."
elif [ $sec1 -lt $sec2 ]; then
    echo "Datum $date1 is eerder dan $date2."
else
    echo "Datum $date1 is later dan $date2."
fi
```

Voorbeelduitvoer als `$date2` later is:

```
Datum 2023-04-01 is eerder dan 2023-04-15.
```

## Diepgaande Duik
Historisch gezien was datums vergelijken in shellscripts niet eenvoudig vanwege verschillende datumformaten en gebrek aan ingebouwde functies. Het `date` commando, met `%s` om datums naar seconden te converteren sinds het Unix-tijdperk (00:00:00 UTC op 1 januari 1970), is een godsgeschenk.

Alternatieven omvatten het gebruik van externe tools zoals `awk` of het doen van string vergelijkingen - riskant als formaten variëren. Wat betreft de implementatie, is één eigenaardigheid het omgaan met tijdzones: het toevoegen van `TZ=UTC` vóór `date` commando’s zorgt voor UTC vergelijkingen.

Datum rekenkunde, zoals het vinden van het verschil tussen datums, kan complex worden. Het toevoegen of aftrekken van dagen vereist meer `date` slimmigheden. Bijzondere situaties, zoals schrikkelseconden of overgangen naar zomertijd, kunnen fouten introduceren.

## Zie Ook
- [`date` man pagina](https://man7.org/linux/man-pages/man1/date.1.html) voor format opties.
- [Stack Overflow](https://stackoverflow.com/questions/tagged/bash) voor gemeenschapswijsheid en probleemoplossing.
