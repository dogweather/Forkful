---
title:                "Conversión de una cadena de texto a minúsculas"
aliases:
- es/java/converting-a-string-to-lower-case.md
date:                  2024-01-20T17:38:28.519667-07:00
model:                 gpt-4-1106-preview
simple_title:         "Conversión de una cadena de texto a minúsculas"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/java/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Convertir una cadena de texto a minúsculas en Java significa transformar todos los caracteres en letra pequeña. Esto se hace por consistencia, busquedas insensibles a mayúsculas y minúsculas y al almacenar o comparar datos.

## Cómo Hacerlo:
```java
public class StringToLower {
    public static void main(String[] args) {
        String original = "¡Hola Mundo!";
        String resultado = original.toLowerCase();
        System.out.println(resultado);
    }
}
```
Salida de muestra:
```
¡hola mundo!
```

## Inmersión Profunda
El método `toLowerCase()` en Java tiene sus raíces en el principio de la informática donde normalizar los datos para procesamiento era y sigue siendo esencial. Existen variantes como `toLowerCase(Locale locale)`, que consideran las reglas de localización para caracteres específicos de un idioma. Por ejemplo, la 'İ' mayúscula en turco se convierte en 'i' sin punto, diferente al inglés. 

La implementación de `toLowerCase()` en Java usa el estándar Unicode para el mapeo entre mayúsculas y minúsculas. Además, alternativas como Apache Commons Lang ofrecen métodos como `StringUtils.lowerCase()` que puede ser útil si ya estás trabajando con esa biblioteca.

## Ver También
- [Clase String en Java](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html)
- [Unicode Standard](https://www.unicode.org/standard/standard.html)
- [Apache Commons Lang StringUtils](https://commons.apache.org/proper/commons-lang/apidocs/org/apache/commons/lang3/StringUtils.html)
