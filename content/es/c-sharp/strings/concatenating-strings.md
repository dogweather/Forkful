---
title:                "Concatenación de cadenas de texto"
aliases:
- /es/c-sharp/concatenating-strings/
date:                  2024-01-20T17:34:37.642361-07:00
model:                 gpt-4-1106-preview
simple_title:         "Concatenación de cadenas de texto"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/c-sharp/concatenating-strings.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Concatenar cadenas significa unir dos o más textos en uno solo. Esto es clave cuando necesitamos mostrar mensajes personalizados al usuario o combinar información que viene de diferentes fuentes.

## Cómo Hacerlo:
Veamos diferentes maneras de concatenar cadenas en C#:

```C#
string nombre = "Mundo";
string saludo = "Hola, " + nombre + "!"; // Uso de '+'
Console.WriteLine(saludo); // Hola, Mundo!

string exclamacion = "Qué ";
string dia = "día!";
string emocion = exclamacion + dia; // Otro ejemplo con '+'
Console.WriteLine(emocion); // Qué día!

// Usando String.Format
string formato = String.Format("Dime {0}, cuál es el secreto", nombre);
Console.WriteLine(formato); // Dime Mundo, cuál es el secreto

// Usando interpolación de cadenas desde C# 6
string interpolado = $"La verdad es que, {nombre} es redondo.";
Console.WriteLine(interpolado); // La verdad es que, Mundo es redondo.

// Usando StringBuilder para concatenaciones múltiples
StringBuilder sb = new StringBuilder();
sb.Append("Esto ");
sb.Append("es ");
sb.Append("eficiente.");
Console.WriteLine(sb.ToString()); // Esto es eficiente.
```

## Profundización
Antes de C#, los programadores hacían malabares con funciones en C y C++ para concatenar cadenas, lo que era más propenso a errores y difícil de mantener. 

A lo largo de los años, C# ha ofrecido mejoras para la concatenación de cadenas. Por ejemplo, `String.Format` fue una mejora significativa para formatear cadenas de una manera legible. Sin embargo, desde C# 6, la interpolación de cadenas ha hecho el código aún más limpio y entendible.

En cuanto a alternativas, `StringBuilder` es preferido cuando tienes que realizar muchas concatenaciones, ya que es más eficiente en términos de memoria y rendimiento en comparación con usar el operador `+`.

Cuando concatenas utilizando el operador `+`, C# crea una nueva cadena con cada operación, lo cual no es óptimo. `StringBuilder` maneja esto internamente de una manera más eficiente, especialmente en bucles o concatenaciones repetidas.

## Ver También
Aquí tienes algunos recursos para ampliar tus conocimientos:

- [Documentación oficial de Microsoft - Strings (C# Programming Guide)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
- [Documentación oficial de Microsoft - StringBuilder Class](https://docs.microsoft.com/en-us/dotnet/api/system.text.stringbuilder?view=net-6.0)
