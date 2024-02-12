---
title:                "Uso de matrices asociativas"
aliases:
- es/c-sharp/using-associative-arrays.md
date:                  2024-01-30T19:09:51.806101-07:00
model:                 gpt-4-0125-preview
simple_title:         "Uso de matrices asociativas"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/c-sharp/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## ¿Qué y por qué?

Los arrays asociativos, o diccionarios en C#, te permiten almacenar y administrar pares de claves y valores. Son tu opción predilecta cuando necesitas buscar valores rápidamente basados en un identificador único, haciendo que la gestión de datos sea muy fácil en aplicaciones complejas.

## Cómo hacerlo:

En C#, trabajas con arrays asociativos utilizando la clase `Dictionary<TKey, TValue>`. Aquí tienes un ejemplo rápido para empezar:

```C#
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        // Creando un diccionario
        Dictionary<string, int> cestaDeFrutas = new Dictionary<string, int>();

        // Añadiendo pares clave-valor
        cestaDeFrutas.Add("Manzanas", 5);
        cestaDeFrutas.Add("Naranjas", 10);

        // Accediendo a un valor usando su clave
        Console.WriteLine("Manzanas: " + cestaDeFrutas["Manzanas"]);
        
        // Actualizando un valor
        cestaDeFrutas["Manzanas"] = 7;
        Console.WriteLine("Manzanas Actualizadas: " + cestaDeFrutas["Manzanas"]);
        
        // Eliminando un par clave-valor
        cestaDeFrutas.Remove("Naranjas");

        // Iterando sobre el diccionario
        foreach (var par in cestaDeFrutas)
        {
            Console.WriteLine(par.Key + ": " + par.Value);
        }
    }
}
```
Salida de muestra:
```
Manzanas: 5
Manzanas Actualizadas: 7
Manzanas: 7
```

Este ejemplo muestra cómo crear un diccionario, añadir, acceder, actualizar y eliminar elementos, y cómo iterar sobre él.

## Análisis profundo

El concepto de arrays asociativos se remonta a su uso en lenguajes de scripts como Perl y PHP, donde ofrecen flexibilidad en la gestión de colecciones de datos. En C#, `Dictionary<TKey, TValue>` es la implementación por defecto, introducida en .NET Framework 2.0. Almacena datos en una tabla hash, asegurando búsquedas, adiciones y eliminaciones eficientes.

Sin embargo, vale la pena señalar que, aunque los diccionarios son increíblemente versátiles, no siempre pueden ser tu mejor opción. Para mantener colecciones ordenadas, podrías considerar `SortedDictionary<TKey, TValue>` o `SortedList<TKey, TValue>`, que ofrecen ordenamiento a costa de operaciones de inserción y eliminación más lentas. Para escenarios que demandan seguridad entre hilos, `ConcurrentDictionary<TKey, TValue>` añade sobrecarga pero asegura el acceso seguro desde múltiples hilos sin bloqueo manual.

En última instancia, la elección de una implementación de array asociativo en C# depende de tus necesidades específicas en cuanto a orden, rendimiento y seguridad entre hilos.
