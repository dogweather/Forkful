---
title:                "Avrundning av tal"
date:                  2024-01-26T03:43:40.997551-07:00
model:                 gpt-4-0125-preview
simple_title:         "Avrundning av tal"
programming_language: "C#"
category:             "C#"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/c-sharp/rounding-numbers.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Att avrunda tal innebär att justera dem till det närmaste angivna platsvärdet—tänk dig att du förenklar dem. Programmerare avrundar för att kontrollera precision, förbättra prestanda eller när de visar användarvänliga resultat—som priser som inte behöver tre decimaler.

## Hur man gör:
Här är en returbiljett för att avrunda tal i C#:

```csharp
using System;

public class RoundingExamples
{
    public static void Main()
    {
        double originalNumber = 123.4567;

        // Avrunda till närmaste hela tal
        double rounded = Math.Round(originalNumber);
        Console.WriteLine(rounded); // Utdata: 123

        // Specificera antal decimalplatser
        double roundedTwoDecimalPlaces = Math.Round(originalNumber, 2);
        Console.WriteLine(roundedTwoDecimalPlaces); // Utdata: 123.46

        // Avrunda uppåt oavsett nästa siffra
        double roundedUp = Math.Ceiling(originalNumber);
        Console.WriteLine(roundedUp); // Utdata: 124

        // Avrunda nedåt oavsett nästa siffra
        double roundedDown = Math.Floor(originalNumber);
        Console.WriteLine(roundedDown); // Utdata: 123
    }
}
```

## Fördjupning
Förr i tiden var avrundning en barnlek för att trimma beräkningskostnader. Varje cykel räknades, och att trimma tal sparade värdefull tid. Spola fram till modern C#, och det handlar om att hantera doubler och decimals kända benägenhet till precisionfel och visningskonstigheter.

Utöver `Math.Round`, `Math.Floor` och `Math.Ceiling`, låter enumet `MidpointRounding` oss styra ödet för stackars, mittsittande siffror—det är skiljevägen mellan bankregler och rättvisans lekplats av "avrunda halva upp".

För tuffare gäng, som seriösa matematik- eller finansapplikationer, har vi `decimal` över `double`, vilket minskar avrundningsdramat genom att erbjuda högre precision—mindre avrundning, färre problem.

## Se också
- [Officiella C#-dokumentationen om `Math.Round`](https://docs.microsoft.com/en-us/dotnet/api/system.math.round)
- [Stack Overflow: När ska jag använda Double istället för Decimal?](https://stackoverflow.com/questions/1165761/decimal-vs-double-which-one-should-i-use-and-when)
- [IEEE-standarden för flyttalsaritmetik (IEEE 754)](https://sv.wikipedia.org/wiki/IEEE_754)
