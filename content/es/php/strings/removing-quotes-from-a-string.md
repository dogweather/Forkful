---
date: 2024-01-26 03:41:00.538400-07:00
description: "Eliminar comillas de una cadena en PHP significa quitar esos molestos\
  \ caracteres de comillas dobles (`\"`) o simples (`'`) que pueden interferir con\
  \ la\u2026"
lastmod: '2024-03-13T22:44:59.148864-06:00'
model: gpt-4-0125-preview
summary: "Eliminar comillas de una cadena en PHP significa quitar esos molestos caracteres\
  \ de comillas dobles (`\"`) o simples (`'`) que pueden interferir con la l\xF3gica\
  \ de tu c\xF3digo o consultas de bases de datos."
title: Eliminando comillas de una cadena
weight: 9
---

## Cómo hacerlo:
Aquí tienes un ejemplo sencillo utilizando las funciones integradas de PHP:

```php
$quotedString = "'Hola,' dijo ella, \"¡Es un día espléndido!\"";
$unquotedString = str_replace(array("'", "\""), '', $quotedString);
echo $unquotedString; // Muestra: Hola, dijo ella, ¡Es un día espléndido!
```

Simple, ¿verdad? Esta función `str_replace()` toma un array de caracteres para eliminar de la cadena, incluyendo tanto comillas simples como dobles.

## En Profundidad
En los primeros días de PHP, los desarrolladores tenían que ser especialmente cuidadosos con las comillas en las cadenas, especialmente cuando insertaban datos en una base de datos. Las comillas manejadas inadecuadamente podrían llevar a ataques de inyección SQL. Entonces aparecieron las comillas mágicas, una característica que escapaba automáticamente los datos de entrada. Se volvió obsoleta y finalmente se eliminó porque alentaba malas prácticas de codificación y problemas de seguridad.

Ahora, utilizamos funciones como `str_replace()` o regex con `preg_replace()` para patrones más avanzados. Aquí tienes un ejemplo con regex:

```php
$quotedString = "'Hola,' dijo ella, \"¡Es un día espléndido!\"";
$unquotedString = preg_replace('/[\'"]/', '', $quotedString);
echo $unquotedString;
```

Para datos JSON, podrías usar `json_encode()` con opciones como `JSON_UNESCAPED_SLASHES | JSON_UNESCAPED_UNICODE` para evitar barras invertidas extra en tus comillas.

Al implementar, considera casos límite. ¿Qué pasa si tu cadena está destinada a tener ciertas comillas, como diálogos en una historia o pulgadas en medidas? El contexto importa, así que personaliza la eliminación de comillas según el uso previsto de los datos.

## Ver También
- [PHP: str_replace](https://www.php.net/manual/en/function.str-replace.php)
- [PHP: preg_replace](https://www.php.net/manual/en/function.preg-replace.php)
- [PHP: json_encode](https://www.php.net/manual/en/function.json-encode.php)
- [OWASP: Prevención de Inyección SQL](https://owasp.org/www-community/attacks/SQL_Injection)
