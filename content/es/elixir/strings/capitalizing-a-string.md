---
title:                "Capitalizando una cadena de texto"
date:                  2024-02-03T19:04:49.177501-07:00
model:                 gpt-4-0125-preview
simple_title:         "Capitalizando una cadena de texto"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/elixir/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## ¿Qué y Por Qué?

Capitalizar una cadena implica convertir la primera letra de la cadena en mayúscula mientras aseguramos que el resto de las letras estén en minúsculas. Esta acción es comúnmente necesaria para formatear la entrada del usuario o mostrar texto en interfaces de usuario, donde la consistencia y legibilidad son importantes.

## Cómo hacerlo:

Elixir provee una manera directa de capitalizar cadenas utilizando sus funciones integradas sin la necesidad de librerías de terceros. Aquí hay un ejemplo simple:

```elixir
string = "elixir programming"
capitalized_string = String.capitalize(string)
IO.puts capitalized_string
```

Salida:

```
Elixir programming
```

Para casos donde se necesita más control o una lógica de capitalización más compleja, podrías combinar diferentes funciones de String. Por ejemplo, si quieres capitalizar cada palabra en una oración, puedes dividir la oración en palabras, capitalizar cada una y luego unirlas de nuevo:

```elixir
sentence = "elixir is fun"
capitalized_sentence = sentence 
                        |> String.split() 
                        |> Enum.map(&String.capitalize/1) 
                        |> Enum.join(" ")

IO.puts capitalized_sentence
```

Salida:

```
Elixir Is Fun
```

Aunque la biblioteca estándar de Elixir cubre la mayoría de las necesidades, para manipulaciones de texto más matizadas, incluyendo capitalización avanzada de cadenas, podrías explorar librerías de terceros como Cldr para internacionalización, que pueden ofrecer comportamientos de capitalización específicos del idioma.
