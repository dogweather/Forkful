---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:54.577326-07:00
description: "YAML, das f\xFCr \"YAML Ain't Markup Language\" steht, ist ein menschenlesbares\
  \ Daten-Serialisierungsformat. Programmierer nutzen es h\xE4ufig f\xFCr\u2026"
lastmod: '2024-03-13T22:44:53.908974-06:00'
model: gpt-4-0125-preview
summary: "YAML, das f\xFCr \"YAML Ain't Markup Language\" steht, ist ein menschenlesbares\
  \ Daten-Serialisierungsformat."
title: Arbeiten mit YAML
weight: 41
---

## Wie:
C# unterstützt YAML nicht standardmäßig, aber Sie können ganz einfach mit YAML arbeiten, indem Sie Drittanbieter-Bibliotheken wie *YamlDotNet* verwenden. Zuerst müssen Sie das YamlDotNet-Paket installieren:

```bash
Install-Package YamlDotNet -Version 11.2.1
```

### YAML lesen:
Stellen Sie sich vor, Sie haben eine YAML-Datei `config.yaml` mit folgendem Inhalt:
```yaml
appSettings:
  name: MyApp
  version: 1.0.0
```

Sie können diese YAML-Datei in C# so lesen und parsen:
```csharp
using System;
using System.IO;
using YamlDotNet.Serialization;
using YamlDotNet.Serialization.NamingConventions;

public class AppConfig
{
    public AppSettings appSettings { get; set; }
}

public class AppSettings
{
    public string name { get; set; }
    public string version { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        var yaml = File.ReadAllText("config.yaml");
        var deserializer = new DeserializerBuilder()
            .WithNamingConvention(UnderscoredNamingConvention.Instance) // Passen Sie die Namenskonvention entsprechend an
            .Build();

        var config = deserializer.Deserialize<AppConfig>(yaml);

        Console.WriteLine($"Name: {config.appSettings.name}, Version: {config.appSettings.version}");
    }
}
```
**Beispielausgabe:**
```
Name: MyApp, Version: 1.0.0
```

### YAML schreiben:
Um Daten in eine YAML-Datei zu schreiben, verwenden Sie die `Serializer`-Klasse von YamlDotNet. So serialisieren Sie ein Objekt zurück in YAML:

```csharp
using System;
using System.IO;
using YamlDotNet.Serialization;
using YamlDotNet.Serialization.NamingConventions;

class Program
{
    static void Main(string[] args)
    {
        var config = new AppConfig
        {
            appSettings = new AppSettings
            {
                name = "MyApp",
                version = "2.0.0"
            }
        };

        var serializer = new SerializerBuilder()
            .WithNamingConvention(UnderscoredNamingConvention.Instance) // Passen Sie die Namenskonvention entsprechend an
            .Build();

        var yaml = serializer.Serialize(config);
        File.WriteAllText("updatedConfig.yaml", yaml);

        Console.WriteLine(yaml);
    }
}
```
**Beispielausgabe:**
```yaml
appSettings:
  name: MyApp
  version: 2.0.0
```

Dieser unkomplizierte Ansatz zeigt, wie Sie effizient mit YAML in Ihren C#-Projekten arbeiten können, indem es einfach gemacht wird, YAML-Dateien mit der YamlDotNet-Bibliothek zu lesen und zu schreiben.
