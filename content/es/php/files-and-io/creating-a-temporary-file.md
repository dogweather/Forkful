---
date: 2024-01-20 17:40:51.548537-07:00
description: "Crear un archivo temporal es simplemente generar un fichero que solo\
  \ necesitas durante la ejecuci\xF3n de tu script PHP. Los programadores lo hacen\
  \ para no\u2026"
lastmod: '2024-03-13T22:44:59.179736-06:00'
model: gpt-4-1106-preview
summary: "Crear un archivo temporal es simplemente generar un fichero que solo necesitas\
  \ durante la ejecuci\xF3n de tu script PHP."
title: Creando un archivo temporal
weight: 21
---

## Cómo hacerlo:
Generar un archivo temporal en PHP es pan comido con la función `tmpfile()`:

```PHP
<?php
$temporal = tmpfile();
fwrite($temporal, "Guardando datos temporalmente aquí...");
rewind($temporal); // Vuelve al inicio del archivo

// Leer y mostrar el contenido del archivo temporal
echo fread($temporal, 1024);

// El archivo se eliminará automáticamente al cerrarse
fclose($temporal);
?>
```

Si ejecutas esto verás el output:
```
Guardando datos temporalmente aquí...
```

## Inmersión Profunda:
Antes de `tmpfile()`, guardar datos sin afectar el sistema de archivos era un baile entre crear y borrar archivos, propenso a errores. Además, `tempnam()` y `sys_get_temp_dir()` son alternativas que permiten más control, creando un archivo temporal con nombre pero que requiere eliminación manual.

La función `tmpfile()` de PHP es una solución segura y fácil, creando un archivo con un nombre único en el directorio temporal del sistema, y lo mejor, se elimina automáticamente al cerrar el recurso (o cuando el script PHP acaba).

## Ver También:
- Documentación oficial de PHP sobre `tmpfile()`: https://www.php.net/manual/es/function.tmpfile.php
- Función `tempnam()`: https://www.php.net/manual/es/function.tempnam.php
- Función `sys_get_temp_dir()`: https://www.php.net/manual/es/function.sys-get-temp-dir.php
