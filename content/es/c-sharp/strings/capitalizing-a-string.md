---
title:                "Capitalizando una cadena de texto"
date:                  2024-02-03T19:05:06.106282-07:00
model:                 gpt-4-0125-preview
simple_title:         "Capitalizando una cadena de texto"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/c-sharp/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## ¿Qué y Por Qué?
Capitalizar una cadena en C# implica convertir el primer carácter de una cadena a mayúsculas si ya no lo está. Esta alteración puede ser crucial para formatear salidas, hacer cumplir estándares de codificación o hacer los textos de la interfaz de usuario más legibles.

## Cómo hacerlo:
C# ofrece un enfoque directo para capitalizar cadenas usando métodos incorporados. La forma más simple de lograr esto es modificando directamente la cadena con estos métodos. Para reglas de capitalización más complejas o específicas (por ejemplo, capitalizar cada palabra), podrían ser necesarias bibliotecas adicionales o métodos manuales. A continuación, se muestran ejemplos que demuestran cómo capitalizar una cadena de diversas maneras en C#.

### Capitalización Básica:
Para capitalizar la primera letra de una sola palabra o frase:

```csharp
string originalString = "hello world";
string capitalizedString = char.ToUpper(originalString[0]) + originalString.Substring(1);
Console.WriteLine(capitalizedString); // Salida: "Hello world"
```

### Capitalizar Cada Palabra:
Para capitalizar la primera letra de cada palabra en una cadena, puedes usar el método `TextInfo.ToTitleCase` que se encuentra en el espacio de nombres `System.Globalization`:

```csharp
using System;
using System.Globalization;

string originalString = "hello world";
TextInfo textInfo = CultureInfo.CurrentCulture.TextInfo;
string capitalizedString = textInfo.ToTitleCase(originalString);
Console.WriteLine(capitalizedString); // Salida: "Hello World"
```

Nota: `ToTitleCase` no cambia a minúsculas el resto de las letras; solo cambia a mayúsculas la primera letra de cada palabra. Además, ciertas palabras en las reglas de mayúsculas de título (como "and", "or", "of") pueden no ser capitalizadas dependiendo de la configuración cultural.

### Usando Métodos de Extensión para la Reutilización:
Puedes crear un método de extensión para la clase `string` para simplificar el proceso de capitalización, haciendo que tu código sea más limpio y reutilizable. Así es como puedes crear y usar tal método:

```csharp
using System;

public static class StringExtensions
{
    public static string Capitalize(this string input)
    {
        if (string.IsNullOrEmpty(input))
        {
            return input;
        }
        return char.ToUpper(input[0]) + input.Substring(1);
    }
}

class Program
{
    static void Main(string[] args)
    {
        string originalString = "hello world";
        string capitalizedString = originalString.Capitalize();
        Console.WriteLine(capitalizedString); // Salida: "Hello world"
    }
}
```

Este método de extensión `Capitalize` se puede llamar en cualquier objeto de cadena dentro del espacio de nombres, ofreciendo un enfoque más intuitivo y orientado a objetos para la manipulación de cadenas en C#.

### Bibliotecas de Terceros:
Aunque la biblioteca estándar de C# cubre la mayoría de las necesidades para la capitalización de cadenas, ciertas tareas especializadas podrían beneficiarse de bibliotecas de terceros, como Humanizer. Sin embargo, para la tarea de simplemente capitalizar cadenas o cada palabra en una cadena, los métodos estándar de C# son adecuados y eficientes, negando la necesidad de dependencias externas.
