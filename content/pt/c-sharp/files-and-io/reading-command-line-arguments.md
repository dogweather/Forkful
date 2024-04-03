---
date: 2024-01-20 17:55:36.651159-07:00
description: "Ler argumentos da linha de comando significa capturar os dados fornecidos\
  \ quando um programa \xE9 iniciado no terminal. Programadores fazem isso para\u2026"
lastmod: '2024-03-13T22:44:46.599153-06:00'
model: gpt-4-1106-preview
summary: "Ler argumentos da linha de comando significa capturar os dados fornecidos\
  \ quando um programa \xE9 iniciado no terminal."
title: Lendo argumentos da linha de comando
weight: 23
---

## Como Fazer:
Aqui está um exemplo simples de como ler argumentos da linha de comando em C#:

```csharp
using System;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Argumentos recebidos:");
        foreach (var arg in args)
        {
            Console.WriteLine(arg);
        }
    }
}
```

Se você salvasse isso como `Program.cs` e executasse `dotnet run arg1 arg2 arg3`, a saída seria:

```
Argumentos recebidos:
arg1
arg2
arg3
```

## Mergulho Profundo:
Nos primórdios, programas de linha de comando eram o padrão. Ler argumentos dessa forma é uma herança dessa época. Alternativamente, há bibliotecas modernas como `CommandLineParser` que ajudam a gerenciar argumentos de forma mais sofisticada. Detalhes importantes sobre a implementação em C# incluem a manipulação do array `args` no método `Main`, que pode ser manipulado como qualquer array em C# para extrair informações conforme necessário.

## Ver Também:
- Documentação Oficial da Microsoft sobre argumentos da linha de comando: [docs.microsoft.com](https://docs.microsoft.com/en-us/dotnet/core/tutorials/cli-create-console-app)
- GitHub do `CommandLineParser`: [CommandLineParser GitHub](https://github.com/commandlineparser/commandline)
