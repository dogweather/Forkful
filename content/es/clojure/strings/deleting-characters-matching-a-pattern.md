---
title:                "Eliminando caracteres que coinciden con un patrón"
date:                  2024-01-20T17:41:46.947632-07:00
model:                 gpt-4-1106-preview
simple_title:         "Eliminando caracteres que coinciden con un patrón"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/clojure/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Eliminar caracteres según un patrón es filtrar ciertos caracteres de una cadena de texto, dejando solo los que necesitamos. Los programadores lo hacen para limpiar y preparar datos, como quitar espacios o caracteres especiales antes de procesarlos.

## Cómo hacerlo:
```Clojure
(defn eliminar-patron [texto patron]
  (clojure.string/replace texto patron ""))

;; Ejemplo de uso:
(println (eliminar-patron "H3llo W0rld!" #"[0-9]"))
(println (eliminar-patron "Clojure es 1 2 3 genial" #"\d"))

;; Salida esperada:
;; "Hllo Wrld!"
;; "Clojure es   genial"
```

## Profundizando
Antes de Clojure, lenguajes como Perl o Python ya manejaban eliminación de caracteres con expresiones regulares. ¿Por qué importa? Porque Clojure no reinventó la rueda, tomó lo bueno y lo integró a su estilo. Alternativas: puedes usar funciones de alto nivel como `filter`, pero las regex son más potentes y concisas para esto. A nivel de implementación, el uso de expresiones regulares en Clojure se apoya en la biblioteca de Java, que es robusta y bien probada.

## Ver También
- Expresiones regulares en Clojure: [Clojure Regex](https://clojure.org/guides/learn/functions#_regex)
- Tutorial de Java Regex, útil para entender el funcionamiento de fondo: [Java Regex Tutorial](https://docs.oracle.com/javase/tutorial/essential/regex/)
