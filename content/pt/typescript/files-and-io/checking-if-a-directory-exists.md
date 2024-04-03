---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:08:43.948977-07:00
description: "Verificar se um diret\xF3rio existe em TypeScript \xE9 essencial para\
  \ tarefas de gerenciamento de arquivos, como ler ou escrever dados em arquivos,\
  \ garantindo\u2026"
lastmod: '2024-03-13T22:44:46.340333-06:00'
model: gpt-4-0125-preview
summary: "Verificar se um diret\xF3rio existe em TypeScript \xE9 essencial para tarefas\
  \ de gerenciamento de arquivos, como ler ou escrever dados em arquivos, garantindo\
  \ que opera\xE7\xF5es sejam realizadas apenas em diret\xF3rios v\xE1lidos."
title: "Verificando se um diret\xF3rio existe"
weight: 20
---

## Como Fazer:
TypeScript, quando executado em um ambiente Node.js, permite verificar se um diretório existe usando o módulo `fs`, que fornece a função `existsSync()` ou a função assíncrona `access()` combinada com `constants.F_OK`.

### Usando `fs.existsSync()`:
```typescript
import { existsSync } from 'fs';

const directoryPath = './caminho/para/diretorio';

if (existsSync(directoryPath)) {
  console.log('O diretório existe.');
} else {
  console.log('O diretório não existe.');
}
```

### Usando `fs.access()` com `fs.constants.F_OK`:
```typescript
import { access, constants } from 'fs';

const directoryPath = './caminho/para/diretorio';

access(directoryPath, constants.F_OK, (err) => {
  if (err) {
    console.log('O diretório não existe.');
    return;
  }
  console.log('O diretório existe.');
});
```

**Saída de Exemplo** para ambos os métodos, assumindo que o diretório exista:
```
O diretório existe.
```

E se não existir:
```
O diretório não existe.
```

### Usando uma Biblioteca de Terceiros - `fs-extra`:
`fs-extra` é uma biblioteca de terceiros popular que aprimora o módulo `fs` embutido e oferece funções mais convenientes.

```typescript
import { pathExists } from 'fs-extra';

const directoryPath = './caminho/para/diretorio';

pathExists(directoryPath).then(exists => {
  console.log(`O diretório existe: ${exists}`);
});
```

**Saída de Exemplo** quando o diretório existe:
```
O diretório existe: true
```

E se não existir:
```
O diretório existe: false
```
