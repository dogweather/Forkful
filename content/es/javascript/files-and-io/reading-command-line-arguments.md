---
date: 2024-01-20 17:56:27.439377-07:00
description: "Leer argumentos de la l\xEDnea de comandos permite que tu programa en\
  \ JavaScript reciba informaci\xF3n desde el exterior cuando se inicia. Esto es \xFA\
  til, por\u2026"
lastmod: '2024-03-13T22:44:59.473688-06:00'
model: gpt-4-1106-preview
summary: "Leer argumentos de la l\xEDnea de comandos permite que tu programa en JavaScript\
  \ reciba informaci\xF3n desde el exterior cuando se inicia."
title: "Lectura de argumentos de l\xEDnea de comandos"
weight: 23
---

## Cómo:
Node.js te da acceso a los argumentos de la línea de comandos a través de `process.argv`. Vamos directo al código:

```Javascript
// myscript.js

// Imprimimos todos los argumentos de la línea de comandos
process.argv.forEach((val, index) => {
  console.log(`${index}: ${val}`);
});
```

Si corres este script con:

```bash
node myscript.js hola mundo
```

obtendrías:

```
0: path/to/node.exe
1: /path/to/myscript.js
2: hola
3: mundo
```

Para ignorar los dos primeros argumentos (que son el propio Node y el script), haz esto:

```Javascript
// Solo argumentos de usuario
const userArgs = process.argv.slice(2);
console.log(userArgs);
```

Con el mismo comando de antes, ahora verías:

```
[ 'hola', 'mundo' ]
```

## Análisis Profundo
Antes de Node.js, leíamos parámetros en la web con query strings o en otros entornos, con APIs específicas del lenguaje; pero Node.js simplificó todo con `process.argv`.

Si necesitas algo más robusto, hay bibliotecas como `yargs` o `commander` que te ayudan a parsear los argumentos de manera más sofisticada y con menos código propio.

Para acceder a variables de entorno, usarías `process.env`. Ambos, `process.argv` y `process.env`, son parte de la API global de Node.js, por lo que no requieren `require`.

## Ver También
- Documentación de Node.js para `process.argv`: https://nodejs.org/docs/latest/api/process.html#process_process_argv
- `yargs` GitHub repo: https://github.com/yargs/yargs
- `commander` GitHub repo: https://github.com/tj/commander.js
