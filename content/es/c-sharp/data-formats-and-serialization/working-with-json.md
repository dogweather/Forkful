---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:22:00.253775-07:00
description: "Trabajar con JSON (JavaScript Object Notation) implica analizar, generar\
  \ y consultar datos JSON, lo que lo convierte en una habilidad cr\xEDtica para la\u2026"
lastmod: '2024-03-13T22:44:59.098960-06:00'
model: gpt-4-0125-preview
summary: "Trabajar con JSON (JavaScript Object Notation) implica analizar, generar\
  \ y consultar datos JSON, lo que lo convierte en una habilidad cr\xEDtica para la\
  \ programaci\xF3n moderna."
title: Trabajando con JSON
weight: 38
---

## Cómo hacerlo:


### Analizando Cadena JSON a un Objeto
C# proporciona el espacio de nombres `System.Text.Json` para el procesamiento eficiente de JSON. Para analizar una cadena JSON a un objeto de C#, define una clase que coincida con la estructura JSON y usa el método `JsonSerializer.Deserialize`.

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
        // Salida: Name: John, Age: 30
    }
}
```

### Generando JSON desde un Objeto
Para convertir un objeto de C# de vuelta a una cadena JSON, usa el método `JsonSerializer.Serialize`.

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
        // Salida: {"Name":"Jane","Age":25}
    }
}
```

### Usando Newtonsoft.Json
`Newtonsoft.Json` (o Json.NET) es una biblioteca de terceros popular que ofrece más flexibilidad y opciones para la serialización y deserialización de JSON.

Para usar Json.NET, primero debes instalar el paquete `Newtonsoft.Json` a través de NuGet. Luego, puedes deserializar una cadena JSON así:

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
        // Salida: Name: Mike, Age: 22
    }
}
```

Para generar JSON desde un objeto con Json.NET:

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
        // Salida: {"Name":"Ella","Age":28}
    }
}
```

Estos fragmentos ofrecen un inicio rápido para manejar JSON en C#, demostrando tanto las capacidades incorporadas de `System.Text.Json` como las extensas características de `Newtonsoft.Json`.
