---
title:                "Capitalizando uma string"
aliases:
- /pt/typescript/capitalizing-a-string/
date:                  2024-02-03T19:06:41.338634-07:00
model:                 gpt-4-0125-preview
simple_title:         "Capitalizando uma string"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/typescript/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Por Que?
Capitalizar uma string envolve modificar o primeiro caractere de uma string dada para maiúsculo se ele estiver em minúsculo, muitas vezes deixando o resto da string inalterado. Essa operação é tipicamente usada para garantir que substantivos próprios ou o início de frases adiram às regras gramaticais no processamento de texto, fazendo com que as saídas pareçam profissionais e legíveis.

## Como fazer:

TypeScript, sendo um superconjunto de JavaScript, permite várias maneiras de capitalizar strings, variando de abordagens puras de JavaScript a utilização de bibliotecas de terceiros para casos de uso mais complexos ou específicos.

**Abordagem Pura de JavaScript:**

```typescript
function capitalize(str: string): string {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

// Saída de Exemplo:
console.log(capitalize('hello TypeScript!')); // 'Hello TypeScript!'
```

Este método é direto e depende do método `charAt()` para acessar o primeiro caractere da string e `toUpperCase()` para convertê-lo para maiúsculo. O método `slice(1)` então recupera o resto da string, deixando-a inalterada.

**Usando a Biblioteca Lodash:**

Para projetos que já usam a biblioteca [Lodash](https://lodash.com/), você pode utilizar sua função `_.capitalize` para alcançar o mesmo resultado com menos código.

Primeiro, instale o Lodash:

```bash
npm install lodash
```

Então, use-a no seu arquivo TypeScript:

```typescript
import * as _ from 'lodash';

// Saída de Exemplo:
console.log(_.capitalize('hello TypeScript!')); // 'Hello typescript!'
```

Nota: O método `_.capitalize` do Lodash converte o resto da string para minúsculo, o que pode não ser sempre o que você deseja.

**Usando uma Expressão Regular:**

Uma expressão regular pode fornecer uma maneira concisa de capitalizar a primeira letra de uma string, especialmente se você precisar capitalizar a primeira letra de cada palavra em uma string.

```typescript
function capitalizeWords(str: string): string {
  return str.replace(/\b\w/g, char => char.toUpperCase());
}

// Saída de Exemplo:
console.log(capitalizeWords('hello typescript world!')); // 'Hello Typescript World!'
```

Este método usa a função `replace()` para procurar qualquer limite de palavra seguido por um caractere alfanumérico (`\b\w`), capitalizando cada correspondência. É particularmente útil para títulos ou cabeçalhos.
