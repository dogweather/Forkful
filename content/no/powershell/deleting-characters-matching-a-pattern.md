---
title:                "Slette tegn som matcher et mønster"
date:                  2024-01-20T17:43:20.603847-07:00
model:                 gpt-4-1106-preview
simple_title:         "Slette tegn som matcher et mønster"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/powershell/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## What & Why? (Hva & Hvorfor?)
Sletting av tegn som matcher et mønster gjør at vi kan finrense tekst ved å ta vekk uønskede deler, som ekstrategn eller kode. Programmerere gjør dette for å bearbeide data smidig og automatisere tekstbehandlingen.

## How to: (Hvordan:)
```PowerShell
$myString = "Hei, verden! 123 POWERshell!"
# Slett alle tall
$noNumbers = $myString -replace '[0-9]', ''
Write-Output $noNumbers
# Output: Hei, verden!  POWERshell!

# Fjern alt utenom bokstaver
$lettersOnly = $myString -replace '[^a-zA-ZæøåÆØÅ ]', ''
Write-Output $lettersOnly
# Output: Hei verden POWERshell
```

## Deep Dive (Dypdykk)
Sletting av tegn basert på et mønster er ikke nytt. Det stammer fra regulære uttrykk, en kraftig syntaks for tekstmanipulasjon som har sin historie tilbake til 1950-tallet. I PowerShell utføres dette med `-replace` operatoren. Alternativt kan du bruke .NET-klasser som `Regex` for mer komplekse operasjoner. Når du bruker `-replace`, husk at det skaper en ny streng siden strenger i .NET er uforanderlige.

## See Also (Se Også)
- [about_Comparison_Operators](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_Comparison_Operators?view=powershell-7.2)
- [about_Regular_Expressions](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_Regular_Expressions?view=powershell-7.2)
- [RegExr](https://regexr.com/): et verktøy for å lære og teste regulære uttrykk.
