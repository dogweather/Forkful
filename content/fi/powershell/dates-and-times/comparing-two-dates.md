---
title:                "Kahden päivämäärän vertailu"
aliases:
- /fi/powershell/comparing-two-dates/
date:                  2024-01-20T17:33:36.252319-07:00
model:                 gpt-4-1106-preview
simple_title:         "Kahden päivämäärän vertailu"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/powershell/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why? - Mitä ja Miksi?
Vertaamme kahta päivämäärää nähdäksemme niiden ajallisen järjestyksen tai aikaeron. Ohjelmoijat tekevät tätä aikataulujen hallinnassa, määräaikojen tarkistuksessa tai muutosten lokitiedostojen analysoinnissa.

## How to: - Kuinka:
Vertailu PowerShellissa:

```PowerShell
# Aseta päivämäärät
$pvm1 = Get-Date '2023-01-01'
$pvm2 = Get-Date '2023-12-31'

# Vertaile päivämääriä
if ($pvm1 -lt $pvm2) {
    Write-Host "$pvm1 on ennen $pvm2"
} elseif ($pvm1 -gt $pvm2) {
    Write-Host "$pvm1 on jälkeen $pvm2"
} else {
    Write-Host "$pvm1 ja $pvm2 ovat samat"
}

# Ero päivämäärien välillä
$ero = $pvm2 - $pvm1
Write-Host "Ero on: $ero"

# Ero päivinä
$päiviä = ($pvm2 - $pvm1).Days
Write-Host "Ero on: $päiviä päivää"
```

Esimerkki tulosteesta:

```
2023-01-01 12:00:00 AM on ennen 2023-12-31 12:00:00 AM
Ero on: 364.00:00:00
Ero on: 364 päivää
```

## Deep Dive - Syväsukellus
Päivämäärien vertailu PowerShellissä käyttää .NET Frameworkin DateTime tyyppejä. Historiallisesti ajatellen, ennen PowerShellia ja .NET:iä, päivämäärien vertailu oli haastavampaa ja yleensä toteutettiin merkkijonojen käsittelyä käyttäen.

Vaihtoehtoiset tavat vertailla päivämääriä PowerShellissä voi sisältää käyttäen `[datetime]`-tyyppisiä metodeja, kuten `.CompareTo()` tai käyttäen lisämoduuleja, kuten `New-TimeSpan`. Myös kulttuurisidonnaiset päivämäärämuodot huomioidaan, joten ole tarkkana niiden kanssa!

Vertailu perustuu todelliseen aikaleimaan, joten aikavyöhykkeet ja kesäaika saattavat vaikuttaa lopputulokseen. Muista ottaa myös huomioon aikaleiman tarkkuus - jos kellonajat ovat tärkeitä, varmista, että ne ovat osa vertailua.

## See Also - Katso Myös
- .NET:n DateTime dokumentaatio: [DateTime Struct](https://docs.microsoft.com/en-us/dotnet/api/system.datetime)
- Aikaerojen laskeminen: [New-TimeSpan Cmdlet](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/new-timespan)
