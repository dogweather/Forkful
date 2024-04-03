---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:37.494989-07:00
description: "Verificar si un directorio existe en JavaScript es esencial para las\
  \ tareas de manipulaci\xF3n de archivos, permitiendo a los scripts verificar la\
  \ presencia\u2026"
lastmod: '2024-03-13T22:44:59.472649-06:00'
model: gpt-4-0125-preview
summary: "Verificar si un directorio existe en JavaScript es esencial para las tareas\
  \ de manipulaci\xF3n de archivos, permitiendo a los scripts verificar la presencia\
  \ del directorio antes de leerlo o escribir en \xE9l."
title: Comprobando si un directorio existe
weight: 20
---

## Cómo hacerlo:
En Node.js, dado que JavaScript en sí mismo no tiene acceso directo al sistema de archivos, el módulo `fs` es típicamente utilizado para tales operaciones. Aquí tienes una manera simple de verificar si un directorio existe utilizando `fs.existsSync()`:

```javascript
const fs = require('fs');

const directoryPath = './sample-directory';

// Verificar si el directorio existe
if (fs.existsSync(directoryPath)) {
  console.log('El directorio existe.');
} else {
  console.log('El directorio no existe.');
}
```
**Salida de Ejemplo:**
```
El directorio existe.
```
O, para un enfoque asíncrono no bloqueante, utiliza `fs.promises` con `async/await`:

```javascript
const fs = require('fs').promises;

async function checkDirectory(directoryPath) {
  try {
    await fs.access(directoryPath);
    console.log('El directorio existe.');
  } catch (error) {
    console.log('El directorio no existe.');
  }
}

checkDirectory('./sample-directory');
```
**Salida de Ejemplo:**
```
El directorio existe.
```

Para proyectos que hacen uso intensivo de operaciones de archivos y directorios, el paquete `fs-extra`, una extensión del módulo nativo `fs`, ofrece métodos adicionales convenientes. Así es cómo puedes lograr lo mismo con `fs-extra`:

```javascript
const fs = require('fs-extra');

const directoryPath = './sample-directory';

// Verificar si el directorio existe
fs.pathExists(directoryPath)
  .then(existe => console.log(existe ? 'El directorio existe.' : 'El directorio no existe.'))
  .catch(err => console.error(err));
```
**Salida de Ejemplo:**
```
El directorio existe.
```

Este enfoque permite un código limpio y legible que se integra a la perfección con las prácticas modernas de JavaScript.
