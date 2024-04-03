---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:19.699380-07:00
description: "Trabajar con CSV (Valores Separados por Comas) implica la lectura y\
  \ escritura de archivos CSV, un formato com\xFAn de intercambio de datos utilizado\
  \ debido a\u2026"
lastmod: '2024-03-13T22:44:58.826135-06:00'
model: gpt-4-0125-preview
summary: "Trabajar con CSV (Valores Separados por Comas) implica la lectura y escritura\
  \ de archivos CSV, un formato com\xFAn de intercambio de datos utilizado debido\
  \ a su simplicidad y amplio soporte a trav\xE9s de diversas plataformas e idiomas."
title: Trabajando con CSV
weight: 37
---

## Cómo hacerlo:
En TypeScript, puedes trabajar con archivos CSV mediante código nativo o aprovechando bibliotecas de terceros como `csv-parser` para leer y `csv-writer` para escribir archivos CSV.

### Leyendo CSV con `csv-parser`
Primero, instala `csv-parser` a través de npm:

```
npm install csv-parser
```

Luego, lee un archivo CSV así:

```typescript
import fs from 'fs';
import csv from 'csv-parser';

const results = [];

fs.createReadStream('data.csv')
  .pipe(csv())
  .on('data', (data) => results.push(data))
  .on('end', () => {
    console.log(results);
    // Salida: Array de objetos, cada uno representando una fila en el CSV
  });
```

Asumiendo que `data.csv` contiene:

```
name,age
Alice,30
Bob,25
```

La salida será:

```
[ { name: 'Alice', age: '30' }, { name: 'Bob', age: '25' } ]
```

### Escribiendo CSV con `csv-writer`
Para escribir en un archivo CSV, primero instala `csv-writer`:

```
npm install csv-writer
```

Luego, úsalo de la siguiente manera:

```typescript
import { createObjectCsvWriter as createCsvWriter } from 'csv-writer';

const csvWriter = createCsvWriter({
  path: 'out.csv',
  header: [
    {id: 'name', title: 'NOMBRE'},
    {id: 'age', title: 'EDAD'}
  ]
});

const data = [
  { name: 'Alice', age: 30 },
  { name: 'Bob', age: 25 }
];

csvWriter
  .writeRecords(data)
  .then(() => console.log('El archivo CSV se escribió con éxito'));
```

Este código escribe lo siguiente en `out.csv`:

```
NOMBRE,EDAD
Alice,30
Bob,25
```

Estos ejemplos muestran cómo integrar el procesamiento de CSV en tus proyectos de TypeScript de manera eficiente, ya sea para el análisis de datos o la persistencia de datos de aplicaciones externamente.
