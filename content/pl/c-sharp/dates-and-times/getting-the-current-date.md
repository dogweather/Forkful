---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:16.021710-07:00
description: "Pobieranie bie\u017C\u0105cej daty w C# polega na uzyskaniu obecnych\
  \ informacji o dacie i czasie z systemu. Programi\u015Bci cz\u0119sto musz\u0105\
  \ uzyska\u0107 dost\u0119p do tych\u2026"
lastmod: '2024-03-13T22:44:35.418794-06:00'
model: gpt-4-0125-preview
summary: "Pobieranie bie\u017C\u0105cej daty w C# polega na uzyskaniu obecnych informacji\
  \ o dacie i czasie z systemu."
title: Pobieranie aktualnej daty
weight: 29
---

## Jak to zrobić:
C# oferuje prosty sposób na pobranie bieżącej daty za pomocą klasy `DateTime`, która jest częścią przestrzeni nazw System w .NET Framework. Poniższy przykład demonstruje, jak pobrać bieżącą datę, i opcjonalnie, czas.

```csharp
using System;

class Program
{
    static void Main()
    {
        // Pobiera tylko bieżącą datę
        DateTime currentDate = DateTime.Today;
        Console.WriteLine(currentDate.ToString("d"));  // Wynik: MM/dd/yyyy
        
        // Pobiera bieżącą datę i czas
        DateTime currentDateTime = DateTime.Now;
        Console.WriteLine(currentDateTime.ToString()); // Wynik: MM/dd/yyyy HH:mm:ss

        // Pobiera bieżącą datę i czas UTC
        DateTime currentUtcDateTime = DateTime.UtcNow;
        Console.WriteLine(currentUtcDateTime.ToString()); // Wynik: MM/dd/yyyy HH:mm:ss
    }
}
```

Jeśli chodzi o biblioteki stron trzecich, NodaTime oferuje solidną alternatywę dla manipulacji datą i czasem, w tym pobieranie bieżącej daty w różnych kalendarzach i strefach czasowych.

```csharp
using NodaTime;
using System;

class Program
{
    static void Main()
    {
        // Korzystanie z NodaTime do pobrania bieżącej daty w kalendarzu ISO
        LocalDate currentDate = SystemClock.Instance.GetCurrentInstant().InUtc().Date;
        Console.WriteLine(currentDate.ToString()); // Wynik: yyyy-MM-dd

        // Dla dat specyficznych dla strefy czasowej
        DateTimeZone zone = DateTimeZoneProviders.Tzdb["America/New_York"];
        LocalDate currentZonedDate = SystemClock.Instance.GetCurrentInstant().InZone(zone).Date;
        Console.WriteLine(currentZonedDate.ToString()); // Wynik: yyyy-MM-dd
    }
}
```

Pokazuje to podstawowe użycie z wbudowaną klasą `DateTime` oraz zaawansowane możliwości oferowane przez NodaTime, szczególnie przydatne dla aplikacji wymagających obsługi różnych stref czasowych lub systemów kalendarzowych.
