---
aliases:
- /fi/powershell/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:31:34.019672-07:00
description: "Lasketaan tulevaisuuden tai menneisyyden p\xE4iv\xE4m\xE4\xE4r\xE4:\
  \ ohjelmoijat tekev\xE4t t\xE4t\xE4, kun tarvitaan erityisp\xE4ivien k\xE4sittely\xE4\
  \ tai aikajaksojen laskentaa."
lastmod: 2024-02-18 23:09:07.868474
model: gpt-4-1106-preview
summary: "Lasketaan tulevaisuuden tai menneisyyden p\xE4iv\xE4m\xE4\xE4r\xE4: ohjelmoijat\
  \ tekev\xE4t t\xE4t\xE4, kun tarvitaan erityisp\xE4ivien k\xE4sittely\xE4 tai aikajaksojen\
  \ laskentaa."
title: "Tulevan tai menneen p\xE4iv\xE4m\xE4\xE4r\xE4n laskeminen"
---

{{< edit_this_page >}}

## What & Why?
Lasketaan tulevaisuuden tai menneisyyden päivämäärä: ohjelmoijat tekevät tätä, kun tarvitaan erityispäivien käsittelyä tai aikajaksojen laskentaa.

## How to:

Laske päivä 10 päivän päähän:

```PowerShell
$Tulevaisuus = (Get-Date).AddDays(10)
$Tulevaisuus
```

Laske päivä 10 päivää menneisyyteen:

```PowerShell
$Menneisyys = (Get-Date).AddDays(-10)
$Menneisyys
```

## Deep Dive
PowerShellissa päivämäärälaskenta onnistuu helposti `Get-Date`-komennon avulla, joka on osa järjestelmän automaattista toimintaa. Ennen PowerShellia ja .NET Frameworkia tämä olisi vaatinut monimutkaisempia laskutoimituksia ja funktioita.

Vaihtoehtoja:
- Käytä `.NET`-luokkaa `[DateTime]` suoraan.
- Vanhemmissa skriptikielissä, kuten batch skripteissä, laskenta on ollut hankalampaa.

Yksityiskohdat:
- `Get-Date` tuottaa nykyisen ajan ja päivämäärän.
- `AddDays()` metodi hyväksyy myönteisiä arvoja tulevaisuuden päivämäärien laskentaan ja kielteisiä arvoja menneisyyden päivämäärien laskentaan.

## See Also
- [PowerShell-dokumentaatio Get-Date -komennosta](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)
- [.NET DateTime -dokumentaatio](https://docs.microsoft.com/dotnet/api/system.datetime)
