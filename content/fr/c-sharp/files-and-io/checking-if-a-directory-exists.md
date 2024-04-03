---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:07.612132-07:00
description: "V\xE9rifier l'existence d'un r\xE9pertoire en C# consiste \xE0 confirmer\
  \ la pr\xE9sence d'un dossier \xE0 un chemin sp\xE9cifique dans le syst\xE8me de\
  \ fichiers. Les\u2026"
lastmod: '2024-03-13T22:44:57.803356-06:00'
model: gpt-4-0125-preview
summary: "V\xE9rifier l'existence d'un r\xE9pertoire en C# consiste \xE0 confirmer\
  \ la pr\xE9sence d'un dossier \xE0 un chemin sp\xE9cifique dans le syst\xE8me de\
  \ fichiers."
title: "V\xE9rifier si un r\xE9pertoire existe"
weight: 20
---

## Comment :


### Utilisation de System.IO
C# fournit l'espace de noms `System.IO` qui contient la classe `Directory`, offrant une manière directe de vérifier l'existence d'un répertoire grâce à la méthode `Exists`.

```csharp
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string directoryPath = @"C:\ExampleDirectory";

        // Vérifier si le répertoire existe
        bool directoryExists = Directory.Exists(directoryPath);

        // Imprimer le résultat
        Console.WriteLine("Le répertoire existe : " + directoryExists);
    }
}
```

**Exemple de sortie :**

```
Le répertoire existe : False
```

Dans le cas où le répertoire existe bien au chemin `C:\ExampleDirectory`, la sortie sera `True`.

### Utilisation de System.IO.Abstractions pour les tests unitaires
Quand il s'agit de rendre votre code testable unitairement, surtout lorsqu'il interagit avec le système de fichiers, le package `System.IO.Abstractions` est un choix populaire. Il vous permet d'abstraire et de simuler les opérations sur le système de fichiers dans vos tests. Voici comment vous pourriez vérifier l'existence d'un répertoire en utilisant cette approche :

D'abord, assurez-vous d'avoir installé le package :

```
Install-Package System.IO.Abstractions
```

Ensuite, vous pouvez injecter un `IFileSystem` dans votre classe et l'utiliser pour vérifier si un répertoire existe, ce qui permet des tests unitaires plus aisés.

```csharp
using System;
using System.IO.Abstractions;

class Program
{
    private readonly IFileSystem _fileSystem;

    public Program(IFileSystem fileSystem)
    {
        _fileSystem = fileSystem;
    }

    public bool CheckDirectoryExists(string directoryPath)
    {
        return _fileSystem.Directory.Exists(directoryPath);
    }

    static void Main()
    {
        var fileSystem = new FileSystem();
        var program = new Program(fileSystem);

        string directoryPath = @"C:\ExampleDirectory";
        bool directoryExists = program.CheckDirectoryExists(directoryPath);

        Console.WriteLine("Le répertoire existe : " + directoryExists);
    }
}
```

**Exemple de sortie :**

```
Le répertoire existe : False
```

Cette approche découple la logique de votre application de l'accès direct au système de fichiers, rendant votre code plus modulaire, testable et maintenable.
