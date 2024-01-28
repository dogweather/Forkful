---
title:                "Eliminando comillas de una cadena"
date:                  2024-01-26T03:41:42.363799-07:00
model:                 gpt-4-0125-preview
simple_title:         "Eliminando comillas de una cadena"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/ruby/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## ¿Qué y por qué?
Quitar las comillas de una cadena significa despojar esos signos de comillas dobles o simples que envuelven los valores de texto. Los programadores a menudo hacen esto para limpiar la entrada del usuario, asegurar la consistencia en el procesamiento de datos o preparar datos para sistemas que podrían confundirse con esos caracteres adicionales.

## Cómo hacerlo:
Ruby tiene algunos trucos ingeniosos bajo la manga para recortar esas molestas comillas. Puedes usar los métodos `gsub` o `delete` para hacer el trabajo. Aquí hay algo de código para masticar:

```ruby
# Usando gsub para eliminar comillas dobles y simples
quoted_string = "\"Say 'hello' to my little friend!\""
unquoted_string = quoted_string.gsub(/'|"/, '')
puts unquoted_string 
# Salida: Say hello to my little friend!

# Si sabes que solo tratarás con un tipo de comilla
single_quoted_string = "'Stay a while and listen!'"
clean_string = single_quoted_string.delete("'")
puts clean_string 
# Salida: Stay a while and listen!
```

## Profundización
La historia de las comillas se remonta a los primeros días de la programación, donde a menudo servían como delimitadores de cadenas. Hoy en día, como entonces, podrías encontrarte necesitando eliminar estos caracteres de comillas cuando no son necesarios o cuando podrían interferir con el almacenamiento y manipulación de datos.

Hemos hablado de `gsub` y `delete` pero hay otros métodos también, como `tr` o `tr_s`, que te dan un poco más de control o pueden manejar algunos casos de uso diferentes:

```ruby
# tr también puede eliminar comillas
double_quoted_string = "\"Do or do not, there is no try.\""
clean_string = double_quoted_string.tr('\"', '')
puts clean_string 
# Salida: Do or do not, there is no try.
```

Recuerda, cada uno de estos métodos tiene sus casos de uso. `gsub` es más poderoso cuando estás tratando con patrones complejos o múltiples sustituciones. `delete` y `tr` funcionan maravillosamente para eliminaciones de caracteres simples y directas.

## Ver también
Para lectura adicional, y para ver estos métodos en acción dentro de bases de código más grandes, echa un vistazo a:
- La documentación de Ruby para [String#gsub](https://ruby-doc.org/core-3.1.2/String.html#method-i-gsub), [String#delete](https://ruby-doc.org/core-3.1.2/String.html#method-i-delete), y [String#tr](https://ruby-doc.org/core-3.1.2/String.html#method-i-tr).
- Ruby Monstas tiene un excelente [conjunto de ejercicios de Strings](http://ruby-for-beginners.rubymonstas.org/built_in_classes/strings.html), que incluye el trabajo con comillas.
- Las discusiones en Stack Overflow sobre [manipulación de cadenas](https://stackoverflow.com/search?q=ruby+remove+quotes+from+string) proporcionan problemas y soluciones del mundo real de compañeros Rubyistas.
