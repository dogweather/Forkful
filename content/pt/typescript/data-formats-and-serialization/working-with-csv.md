---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:24.788856-07:00
description: "Trabalhar com CSV (Valores Separados por V\xEDrgula) envolve a leitura\
  \ e escrita de arquivos CSV, um formato comum de troca de dados usado devido \xE0\
  \ sua\u2026"
lastmod: '2024-03-13T22:44:46.348579-06:00'
model: gpt-4-0125-preview
summary: "Trabalhar com CSV (Valores Separados por V\xEDrgula) envolve a leitura e\
  \ escrita de arquivos CSV, um formato comum de troca de dados usado devido \xE0\
  \ sua simplicidade e ampla compatibilidade entre diversas plataformas e linguagens."
title: Trabalhando com CSV
weight: 37
---

## Como fazer:
Em TypeScript, você pode trabalhar com arquivos CSV por meio de código nativo ou utilizando bibliotecas de terceiros como `csv-parser` para leitura e `csv-writer` para escrita de arquivos CSV.

### Lendo CSV com `csv-parser`
Primeiro, instale o `csv-parser` via npm:

```
npm install csv-parser
```

Em seguida, leia um arquivo CSV assim:

```typescript
import fs from 'fs';
import csv from 'csv-parser';

const results = [];

fs.createReadStream('data.csv')
  .pipe(csv())
  .on('data', (data) => results.push(data))
  .on('end', () => {
    console.log(results);
    // Saída: Array de objetos, cada um representando uma linha no CSV
  });
```

Assumindo que `data.csv` contém:

```
name,age
Alice,30
Bob,25
```

A saída será:

```
[ { name: 'Alice', age: '30' }, { name: 'Bob', age: '25' } ]
```

### Escrevendo CSV com `csv-writer`
Para escrever em um arquivo CSV, primeiro instale o `csv-writer`:

```
npm install csv-writer
```

Depois, use-o da seguinte forma:

```typescript
import { createObjectCsvWriter as createCsvWriter } from 'csv-writer';

const csvWriter = createCsvWriter({
  path: 'out.csv',
  header: [
    {id: 'name', title: 'NOME'},
    {id: 'age', title: 'IDADE'}
  ]
});

const data = [
  { name: 'Alice', age: 30 },
  { name: 'Bob', age: 25 }
];

csvWriter
  .writeRecords(data)
  .then(() => console.log('O arquivo CSV foi escrito com sucesso'));
```

Este código escreve o seguinte em `out.csv`:

```
NOME,IDADE
Alice,30
Bob,25
```

Estes exemplos mostram como integrar o processamento de CSV nos seus projetos TypeScript de maneira eficiente, seja lendo dados para análise ou persistindo dados de aplicação externamente.
