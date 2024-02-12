---
title:                "Een string omzetten naar kleine letters"
aliases:
- /nl/powershell/converting-a-string-to-lower-case/
date:                  2024-01-28T21:57:49.550942-07:00
model:                 gpt-4-0125-preview
simple_title:         "Een string omzetten naar kleine letters"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/powershell/converting-a-string-to-lower-case.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Een string omzetten naar kleine letters betekent dat elke letter in de string een kleine letter wordt. Programmeurs doen dit om tekst te standaardiseren, vergelijkingen te maken, en soms om te voldoen aan hoofdlettergevoelige regels in codering of gegevensopslag.

## Hoe:

PowerShell is vrij handig met strings. Gebruik de `.ToLower()` methode, zoals dit:

```PowerShell
$string = "HELLO, World!"
$lowerCaseString = $string.ToLower()
$lowerCaseString
```

Uitvoer:

```
hello, world!
```

Of probeer de `ToLowerInvariant()` methode wanneer culturele normen de conversie niet zouden moeten beïnvloeden:

```PowerShell
$string = "HELLO, World!"
$lowerCaseInvariant = $string.ToLowerInvariant()
$lowerCaseInvariant
```

Uitvoer:

```
hello, world!
```

## Diepgaand

Er was een tijd dat hoofdletterongevoeligheid vrij gebruikelijk was in programmeertalen. In PowerShell, zoals zijn .NET voorgangers, zijn strings objecten met ingebouwde methoden voor manipulatie. Wanneer we `.ToLower()` gebruiken, roepen we een methode op die het conversieproces voor ons afhandelt.

Alternatieve manieren om het werk gedaan te krijgen? Zeker. Je zou kunnen gebruiken:

- een `for` lus, elk karakter bezoeken en handmatig van geval veranderen
- Reguliere Expressies met de `-replace` operator
- Cultuurspecifieke conversies met behulp van overloads van `.ToLower()`

Waarom de invariante cultuur gebruiken met `ToLowerInvariant()`? Het is essentieel voor consistente resultaten over verschillende locales waar de interpretatie van wat een "kleine" letter is, kan verschillen.

## Zie Ook

Voor meer gedetailleerde avonturen in stringmanipulatie, bezoek deze links:

- [.NET String Class](https://docs.microsoft.com/en-us/dotnet/api/system.string?view=net-6.0)
