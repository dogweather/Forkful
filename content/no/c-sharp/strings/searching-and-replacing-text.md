---
aliases:
- /no/c-sharp/searching-and-replacing-text/
date: 2024-01-20 17:57:20.434006-07:00
description: "S\xF8k og erstatt tekst er prosessen med \xE5 finne strenger innenfor\
  \ en tekst og bytte dem ut med noe annet. Vi programmerere gj\xF8r dette for \xE5\
  \ endre data,\u2026"
lastmod: 2024-02-18 23:08:53.879296
model: gpt-4-1106-preview
summary: "S\xF8k og erstatt tekst er prosessen med \xE5 finne strenger innenfor en\
  \ tekst og bytte dem ut med noe annet. Vi programmerere gj\xF8r dette for \xE5 endre\
  \ data,\u2026"
title: "S\xF8king og erstatting av tekst"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Søk og erstatt tekst er prosessen med å finne strenger innenfor en tekst og bytte dem ut med noe annet. Vi programmerere gjør dette for å endre data, automatisere redigeringer, eller massemodifisere kode.

## Slik gjør du:
```C#
using System;

class Program
{
    static void Main()
    {
        string originalText = "Hei, verden! Jeg elsker å kode i C#.";
        string searchText = "verden";
        string replaceText = "Norge";

        // Søk og erstatt
        string updatedText = originalText.Replace(searchText, replaceText);

        Console.WriteLine(updatedText);  // Output: "Hei, Norge! Jeg elsker å kode i C#."
    }
}
```

## Dypdykk
Søk og erstatt-operasjoner har vært en grunnleggende del av tekstbehandling siden tidlige databehandlingssystemer. På grunn av sin universelle nytte, er dette en funksjon som er innebygd i mange programmeringsspråk, inkludert C#. 

Metoden `String.Replace` er den rette veien i C# for enkel tekst-manipulasjon. Men hvis du trenger mer komplekse søkemønstre, kan du dykke inn i regulære uttrykk (regex), tilgjengelig gjennom `System.Text.RegularExpressions.Regex` klassen.

Alternativt, for filbehandling og masseendringer, kan PowerShell ofte være et bedre verktøy, spesielt for administrative skript.

Implementeringsmessig, husk at `String` i C# er uforanderlig. Det betyr at hver gang du erstatter tekst, skaper du en ny streng i minnet. Ved store tekstmasser eller mange operasjoner kan dette påvirke ytelse og minnebruk.

## Se også
- Microsoft sin dokumentasjon på `String.Replace`: https://docs.microsoft.com/en-us/dotnet/api/system.string.replace
- Regex i C# veiledning: https://docs.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference
- PowerShell-dokumentasjon for tekstmanipulering: https://docs.microsoft.com/en-us/powershell/scripting/how-to/working-with-strings?view=powershell-7.2
