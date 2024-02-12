---
title:                "Capitalizando una cadena de texto"
aliases:
- es/kotlin/capitalizing-a-string.md
date:                  2024-02-03T19:05:35.098660-07:00
model:                 gpt-4-0125-preview
simple_title:         "Capitalizando una cadena de texto"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/kotlin/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Qué y Por Qué?

Capitalizar una cadena en programación implica convertir el primer carácter de la cadena a mayúsculas si aún no lo está, lo cual es útil para formatear entradas de usuarios o mostrar texto en una interfaz de usuario de una manera más estandarizada o amigable para el humano. Los programadores realizan esta operación para asegurar la consistencia de los datos o para cumplir con requisitos de formato específicos dentro de sus aplicaciones de software.

## Cómo:

En Kotlin, las cadenas pueden capitalizarse utilizando las funciones de la biblioteca estándar sin la necesidad de librerías de terceros. El enfoque de Kotlin para manejar cadenas hace que estas operaciones sean directas y concisas.

### Capitalizando toda la cadena:

```kotlin
val message = "hello, world!"
val capitalizedMessage = message.uppercase()

println(capitalizedMessage) // Salida: HELLO, WORLD!
```

### Capitalizando solo el primer carácter:

A partir de Kotlin 1.5, la función `capitalize()` está obsoleta y reemplazada con una combinación de `replaceFirstChar` y una lambda que verifica si es una letra minúscula para transformarla a mayúsculas.

```kotlin
val greeting = "hello, world!"
val capitalizedGreeting = greeting.replaceFirstChar {
    if (it.isLowerCase()) it.titlecase() else it.toString()
}

println(capitalizedGreeting) // Salida: Hello, world!
```

Este enfoque mantiene el resto de la frase en su forma original mientras solo cambia la primera letra a mayúsculas.
