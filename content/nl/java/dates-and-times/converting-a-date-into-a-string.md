---
title:                "Een datum converteren naar een string"
aliases:
- nl/java/converting-a-date-into-a-string.md
date:                  2024-01-28T21:57:27.600328-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een datum converteren naar een string"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/java/converting-a-date-into-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Een datum naar een tekenreeks converteren betekent het vertegenwoordigen van een datumobject als leesbare tekst die een specifiek patroon volgt. Programmeurs doen dit om datums aan gebruikers weer te geven of om ze te serialiseren voor opslag en netwerken in een gebruiksvriendelijk formaat.

## Hoe:

Java maakt de conversie van datum naar tekenreeks eenvoudig. De klasse `java.time.format.DateTimeFormatter` is je eerste keuze. Hier is een codevoorbeeld:

```java
import java.time.LocalDate;
import java.time.format.DateTimeFormatter;

public class DateToStringExample {
    public static void main(String[] args) {
        LocalDate date = LocalDate.now(); // De datum van vandaag
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy");
        String dateString = date.format(formatter);
        System.out.println(dateString); // Output zou bijvoorbeeld kunnen zijn: 20/03/2023
    }
}
```

## Diepgaand

Historisch gezien gebruikte Java `SimpleDateFormat` uit het `java.text` pakket, maar dit was niet thread-safe en leidde tot fouten. Met Java 8 bracht het `java.time` pakket thread-safe en onveranderlijke datum-tijd klassen. `DateTimeFormatter` is onderdeel van dit moderne pakket.

Er zijn alternatieven zoals `FastDateFormat` van Apache Commons en `DateUtils` uit verschillende bibliotheken. Toch houden de meeste Java-ontwikkelaars zich aan de standaardbibliotheek, die robuust en veelzijdig is.

Bij het formatteren gebruikt `DateTimeFormatter` de patronen `yyyy` voor het jaar, `MM` voor de maand en `dd` voor de dag. Het kan behoorlijk complexe patronen aan, zelfs locatiespecifieke, met zijn methode `ofPattern`. Het is ook het vermelden waard dat `DateTimeFormatter` onveranderlijk en thread-safe is, dus je kunt dezelfde formatterinstantie gebruiken in meerdere threads zonder enige synchronisatieprobleem.

## Zie Ook

- Officiële Java docs van Oracle voor `DateTimeFormatter`: https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html
- Voor meer datum- en tijdpatronen: https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#patterns
- Overzicht van Java 8 Datum en Tijd: https://www.oracle.com/technical-resources/articles/java/jf14-date-time.html
