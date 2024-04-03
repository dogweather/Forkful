---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:31:40.492830-07:00
description: "Pisanie test\xF3w w JavaScript odnosi si\u0119 do praktyki tworzenia\
  \ automatycznych skrypt\xF3w, kt\xF3re uruchamiaj\u0105 tw\xF3j kod, aby upewni\u0107\
  \ si\u0119, \u017Ce dzia\u0142a on zgodnie z\u2026"
lastmod: '2024-03-13T22:44:35.800089-06:00'
model: gpt-4-0125-preview
summary: "Pisanie test\xF3w w JavaScript odnosi si\u0119 do praktyki tworzenia automatycznych\
  \ skrypt\xF3w, kt\xF3re uruchamiaj\u0105 tw\xF3j kod, aby upewni\u0107 si\u0119\
  , \u017Ce dzia\u0142a on zgodnie z oczekiwaniami, co mo\u017Ce znacznie poprawi\u0107\
  \ niezawodno\u015B\u0107 i mo\u017Cliwo\u015B\u0107 utrzymania aplikacji."
title: "Pisanie test\xF3w"
weight: 36
---

## Jak to zrobić:


### Natywne podejście (używając Jest)
Jest to popularne narzędzie do testowania, które dostarcza przyjazne API do pisania testów jednostkowych w JavaScript. Wymaga minimalnej konfiguracji i oferuje funkcje takie jak atrapy funkcji, timery i testowanie migawek.

1. **Instalacja**:

```bash
npm install --save-dev jest
```

2. **Pisanie prostego testu**:

Utwórz plik o nazwie `sum.test.js`:

```javascript
const sum = require('./sum'); // Zakładamy, że ta funkcja po prostu dodaje dwie liczby

test('dodaje 1 + 2, żeby otrzymać 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

3. **Uruchamianie testu**:

```bash
npx jest
```

**Przykładowe wyjście:**

```plaintext
PASS  ./sum.test.js
✓ dodaje 1 + 2, żeby otrzymać 3 (5ms)
```

### Testowanie kodu asynchronicznego
Jest ułatwia testowanie obietnic i składni async/await:

```javascript
// asyncSum.js
async function asyncSum(a, b) {
  return Promise.resolve(a + b);
}

// asyncSum.test.js
test('asynchroniczne dodawanie działa', async () => {
  await expect(asyncSum(1, 2)).resolves.toBe(3);
});

```

### Użycie bibliotek stron trzecich (Mocha & Chai)
Mocha to kolejne popularne narzędzie do testowania, często używane z biblioteką asercji Chai dla bardziej ekspresyjnych testów.

1. **Instalacja**:

```bash
npm install --save-dev mocha chai
```

2. **Pisanie testu z wykorzystaniem Mochy i Chai**:

Utwórz `calculate.test.js`:

```javascript
const chai = require('chai');
const expect = chai.expect;

const calculate = require('./calculate'); // Prosty moduł kalkulacyjny

describe('Calculate', function() {
  it('powinien sumować dwie wartości', function() {
    expect(calculate.sum(5, 2)).to.equal(7);
  });
});
```

3. **Uruchamianie testów z Mocha**:

Dodaj skrypt w swoim pliku `package.json`:

```json
"scripts": {
  "test": "mocha"
}
```

Następnie wykonaj:

```bash
npm test
```

**Przykładowe wyjście:**

```plaintext
  Calculate
    ✓ powinien sumować dwie wartości


  1 passing (8ms)
```

Te przykłady ilustrują podstawy pisania i wykonywania testów w JavaScript. Przyjęcie ramy do testowania takiej jak Jest czy Mocha z Chai może zapewnić solidną podstawę do solidnego testowania aplikacji, pomagając zapewnić, że twój kod funkcjonuje zgodnie z zamierzeniami przez aktualizacje i refaktoryzacje.
