---
aliases:
- /sv/c-sharp/writing-to-standard-error/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:32:50.859456-07:00
description: "Att skriva till standardfel (stderr) i C# inneb\xE4r att rikta felmeddelanden\
  \ och diagnostik separat fr\xE5n regulj\xE4r utdata (stdout) f\xF6r att hj\xE4lpa\
  \ anv\xE4ndare\u2026"
lastmod: 2024-02-18 23:08:51.811908
model: gpt-4-0125-preview
summary: "Att skriva till standardfel (stderr) i C# inneb\xE4r att rikta felmeddelanden\
  \ och diagnostik separat fr\xE5n regulj\xE4r utdata (stdout) f\xF6r att hj\xE4lpa\
  \ anv\xE4ndare\u2026"
title: Skriva till standardfel
---

{{< edit_this_page >}}

## Vad & Varför?
Att skriva till standardfel (stderr) i C# innebär att rikta felmeddelanden och diagnostik separat från reguljär utdata (stdout) för att hjälpa användare och utvecklare att skilja mellan normal programutdata och felnotifikationer. Programmerare gör detta för att göra felsökning och loggning mer effektiv, vilket möjliggör smidigare drift och underhåll av applikationer.

## Hur man gör:
I C# kan skrivning till standardfel uppnås genom att använda strömmen `Console.Error`. Denna ström används specifikt för felmeddelanden och diagnostik. Här är ett grundläggande exempel:

```csharp
Console.Error.WriteLine("Error: Misslyckades med att bearbeta förfrågan.");
```

Exempel på utdata (till stderr):
```
Error: Misslyckades med att bearbeta förfrågan.
```

För scenarier där du kanske använder ett tredjepartsbibliotek som erbjuder avancerade loggningsmöjligheter, som `Serilog` eller `NLog`, kan du konfigurera dessa bibliotek för att skriva felloggar till stderr. Även om dessa exempel fokuserar på enkel konsolomdirigering, kom ihåg att i produktionsapplikationer erbjuder loggningsramverk mycket mer robust felhantering och utdatalternativ. Här är ett enkelt exempel med `Serilog`:

Först, installera Serilog-paketet och dess Console sink:

```
Install-Package Serilog
Install-Package Serilog.Sinks.Console
```

Sedan, konfigurera Serilog för att skriva till stderr:

```csharp
using Serilog;

Log.Logger = en ny LoggerConfiguration()
    .WriteTo.Console(standardErrorFromLevel: Serilog.Events.LogEventLevel.Error)
    .CreateLogger();

Log.Information("Det här är ett vanligt meddelande.");
Log.Error("Det här är ett felmeddelande.");
```

Exempel på utdata (till stderr för felmeddelandet):
```
[15:04:20 ERR] Det här är ett felmeddelande.
```

Notera: Konfigurationen `standardErrorFromLevel` i Serilogs console sink omdirigerar alla logghändelser på den angivna nivån (Error, i detta fall) eller högre till standardfelsströmmen, medan meddelanden på lägre nivåer som Information skrivs till standardutströmmen.
