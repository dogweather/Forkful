---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:48.274918-07:00
description: "C#:ssa vakiovirheeseen (stderr) kirjoittaminen tarkoittaa virheviestien\
  \ ja diagnostiikkatietojen ohjaamista erill\xE4\xE4n s\xE4\xE4nn\xF6llisest\xE4\
  \ tulosteesta (stdout)\u2026"
lastmod: '2024-03-13T22:44:56.590386-06:00'
model: gpt-4-0125-preview
summary: "C#:ssa vakiovirheeseen (stderr) kirjoittaminen tarkoittaa virheviestien\
  \ ja diagnostiikkatietojen ohjaamista erill\xE4\xE4n s\xE4\xE4nn\xF6llisest\xE4\
  \ tulosteesta (stdout) auttaakseen k\xE4ytt\xE4ji\xE4 ja kehitt\xE4ji\xE4 erottamaan\
  \ normaalin ohjelman tulosteen ja virheilmoitukset toisistaan."
title: Kirjoittaminen standardivirheeseen
weight: 25
---

## Kuinka:
C#:ssa vakiovirheeseen kirjoittamisen voi saavuttaa käyttämällä `Console.Error`-virtaa. Tätä virtaa käytetään nimenomaan virheviestien ja diagnostiikan varten. Tässä on yksinkertainen esimerkki:

```csharp
Console.Error.WriteLine("Virhe: Pyyntöä ei voitu käsitellä.");
```

Esimerkkituloste (stderriin):
```
Virhe: Pyyntöä ei voitu käsitellä.
```

Skenaarioissa, joissa saatat käyttää kolmannen osapuolen kirjastoa, joka tarjoaa edistyneitä lokitustoimintoja, kuten `Serilog` tai `NLog`, voit määrittää nämä kirjastot kirjoittamaan virhelokit stderriin. Vaikka nämä esimerkit keskittyvät yksinkertaiseen konsolin uudelleenohjaukseen, muista, että tuotantosovelluksissa lokitusrakenteet tarjoavat paljon kestävämpiä virheenkäsittely- ja tulostusvaihtoehtoja. Tässä on yksinkertainen esimerkki `Serilog`:lla:

Ensimmäiseksi, asenna Serilog-paketti ja sen Console-säilö:

```
Install-Package Serilog
Install-Package Serilog.Sinks.Console
```

Sen jälkeen, määritä Serilog kirjoittamaan stderriin:

```csharp
using Serilog;

Log.Logger = new LoggerConfiguration()
    .WriteTo.Console(standardErrorFromLevel: Serilog.Events.LogEventLevel.Error)
    .CreateLogger();

Log.Information("Tämä on normaali viesti.");
Log.Error("Tämä on virheviesti.");
```

Esimerkkituloste (stderrille virheviestille):
```
[15:04:20 ERR] Tämä on virheviesti.
```

Huom: `standardErrorFromLevel`-määritys Serilogin konsolisäilössä ohjaa kaikki lokitapahtumat määritellyllä tasolla (tässä tapauksessa Virhe) tai korkeammalle vakiovirhevuo, kun taas alempitasoiset viestit kuten Tiedot kirjoitetaan vakiotulostevuo.
