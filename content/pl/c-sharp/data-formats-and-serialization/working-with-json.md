---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:22:46.747087-07:00
description: "Praca z JSON (JavaScript Object Notation) obejmuje parsowanie, generowanie\
  \ oraz zapytania o dane JSON, co czyni j\u0105 kluczow\u0105 umiej\u0119tno\u015B\
  ci\u0105 we wsp\xF3\u0142czesnym\u2026"
lastmod: '2024-03-13T22:44:35.430321-06:00'
model: gpt-4-0125-preview
summary: "Praca z JSON (JavaScript Object Notation) obejmuje parsowanie, generowanie\
  \ oraz zapytania o dane JSON, co czyni j\u0105 kluczow\u0105 umiej\u0119tno\u015B\
  ci\u0105 we wsp\xF3\u0142czesnym programowaniu."
title: Praca z JSON
weight: 38
---

## Jak to zrobić:


### Parsowanie ciągu JSON do obiektu
C# dostarcza przestrzeń nazw `System.Text.Json` dla efektywnego przetwarzania JSON. Aby przeprowadzić parsowanie ciągu JSON do obiektu C#, należy zdefiniować klasę, która pasuje do struktury JSON i użyć metody `JsonSerializer.Deserialize`.

```csharp
using System;
using System.Text.Json;

public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
}

public class Program
{
    public static void Main()
    {
        string jsonString = "{\"Name\":\"John\", \"Age\":30}";
        Person person = JsonSerializer.Deserialize<Person>(jsonString);

        Console.WriteLine($"Name: {person.Name}, Age: {person.Age}");
        // Wynik: Name: John, Age: 30
    }
}
```

### Generowanie JSON z obiektu
Aby przekonwertować obiekt C# z powrotem na ciąg JSON, użyj metody `JsonSerializer.Serialize`.

```csharp
using System;
using System.Text.Json;

public class Program
{
    public static void Main()
    {
        Person person = new Person
        {
            Name = "Jane",
            Age = 25
        };

        string jsonString = JsonSerializer.Serialize(person);
        Console.WriteLine(jsonString);
        // Wynik: {"Name":"Jane","Age":25}
    }
}
```

### Użycie Newtonsoft.Json
`Newtonsoft.Json` (lub Json.NET) to popularna biblioteka stron trzecich oferująca większą elastyczność i opcje dla serializacji oraz deserializacji JSON.

Aby użyć Json.NET, musisz najpierw zainstalować pakiet `Newtonsoft.Json` przez NuGet. Następnie można deserializować ciąg JSON w następujący sposób:

```csharp
using System;
using Newtonsoft.Json;

public class Program
{
    public static void Main()
    {
        string jsonString = "{\"Name\":\"Mike\", \"Age\":22}";
        Person person = JsonConvert.DeserializeObject<Person>(jsonString);

        Console.WriteLine($"Name: {person.Name}, Age: {person.Age}");
        // Wynik: Name: Mike, Age: 22
    }
}
```

Aby generować JSON z obiektu przy użyciu Json.NET:

```csharp
using System;
using Newtonsoft.Json;

public class Program
{
    public static void Main()
    {
        Person person = new Person
        {
            Name = "Ella",
            Age = 28
        };

        string jsonString = JsonConvert.SerializeObject(person);
        Console.WriteLine(jsonString);
        // Wynik: {"Name":"Ella","Age":28}
    }
}
```

Te fragmenty kodu oferują szybki start w obsłudze JSON w C#, demonstrując zarówno wbudowane możliwości `System.Text.Json`, jak i rozszerzone funkcjonalności `Newtonsoft.Json`.
