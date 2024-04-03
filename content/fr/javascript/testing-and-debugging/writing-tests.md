---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:31:16.105872-07:00
description: "\xC9crire des tests en JavaScript fait r\xE9f\xE9rence \xE0 la pratique\
  \ de cr\xE9er des scripts automatis\xE9s qui ex\xE9cutent votre code pour garantir\
  \ qu'il se comporte\u2026"
lastmod: '2024-03-13T22:44:58.279605-06:00'
model: gpt-4-0125-preview
summary: "\xC9crire des tests en JavaScript fait r\xE9f\xE9rence \xE0 la pratique\
  \ de cr\xE9er des scripts automatis\xE9s qui ex\xE9cutent votre code pour garantir\
  \ qu'il se comporte comme pr\xE9vu, ce qui peut consid\xE9rablement am\xE9liorer\
  \ la fiabilit\xE9 et la maintenabilit\xE9 de vos applications."
title: "R\xE9daction de tests"
weight: 36
---

## Comment faire :


### Approche native (en utilisant Jest)
Jest est un cadre de test populaire qui fournit une API conviviale pour écrire des tests unitaires en JavaScript. Il nécessite une configuration minimale et vient avec des fonctionnalités comme les fonctions de simulation, les minuteries et les tests instantanés.

1. **Installation** :

```bash
npm install --save-dev jest
```

2. **Écrire un test simple** :

Créez un fichier nommé `sum.test.js` :

```javascript
const sum = require('./sum'); // Supposez que cette fonction ajoute simplement deux nombres

test('ajoute 1 + 2 pour égaler 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

3. **Exécuter votre test** :

```bash
npx jest
```

**Résultat d'exemple :**

```plaintext
PASS  ./sum.test.js
✓ ajoute 1 + 2 pour égaler 3 (5ms)
```

### Tester le code asynchrone
Jest facilite le test des promesses et de la syntaxe async/await :

```javascript
// asyncSum.js
async function asyncSum(a, b) {
  return Promise.resolve(a + b);
}

// asyncSum.test.js
test('l’addition asynchrone fonctionne', async () => {
  await expect(asyncSum(1, 2)).resolves.toBe(3);
});

```

### Utilisation de bibliothèques tierces (Mocha & Chai)
Mocha est un autre cadre de test populaire, souvent utilisé avec la bibliothèque d'assertion Chai pour des tests plus expressifs.

1. **Installation** :

```bash
npm install --save-dev mocha chai
```

2. **Écrire un test avec Mocha et Chai** :

Créez `calculate.test.js` :

```javascript
const chai = require('chai');
const expect = chai.expect;

const calculate = require('./calculate'); // Un module de calcul simple

describe('Calculate', function() {
  it('devrait additionner deux valeurs', function() {
    expect(calculate.sum(5, 2)).to.equal(7);
  });
});
```

3. **Exécuter vos tests avec Mocha** :

Ajoutez un script dans votre `package.json` :

```json
"scripts": {
  "test": "mocha"
}
```

Puis exécutez :

```bash
npm test
```

**Résultat d'exemple :**

```plaintext
  Calculate
    ✓ devrait additionner deux valeurs


  1 passing (8ms)
```

Ces exemples illustrent l'écriture et l'exécution de tests de base en JavaScript. Adopter un cadre de test comme Jest ou Mocha avec Chai peut fournir une base solide pour des tests d'application robustes, aidant à garantir que votre code fonctionne comme prévu à travers les mises à jour et les remaniements.
