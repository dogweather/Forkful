---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:13:14.944002-07:00
description: "Tests schrijven betekent code cre\xEBren die controleert of andere code\
  \ correct werkt. Programmeurs doen dit om bugs vroegtijdig op te vangen, tijd te\u2026"
lastmod: '2024-03-13T22:44:50.554420-06:00'
model: gpt-4-0125-preview
summary: "Tests schrijven betekent code cre\xEBren die controleert of andere code\
  \ correct werkt."
title: Tests Schrijven
weight: 36
---

## Hoe:
Laten we een eenvoudige functie testen met Jest, een populair testraamwerk voor JavaScript en TypeScript.

Installeer eerst Jest met TypeScript-ondersteuning:

```bash
npm install --save-dev jest @types/jest ts-jest
```

Voeg een `jest.config.js` toe:

```js
module.exports = {
  preset: 'ts-jest',
  testEnvironment: 'node',
};
```

Definieer een functie in `math.ts`:

```typescript
export function add(a: number, b: number): number {
  return a + b;
}
```

Schrijf een test in `math.test.ts`:

```typescript
import { add } from './math';

test('telt 1 + 2 op tot 3', () => {
  expect(add(1, 2)).toBe(3);
});
```

Voer tests uit:

```bash
npx jest
```

Voorbeeld output:

```
PASS  ./math.test.ts
✓ telt 1 + 2 op tot 3 (5ms)
```

## Diepere Duik
Testen in TypeScript bouwt voort op JavaScript-testpraktijken. Hier is wat het speciaal maakt:

- Historische context: TypeScript kwam tot leven in 2012. Het was bedoeld om types toe te voegen aan JavaScript, om code makkelijker te onderhouden en te testen.
- Alternatieven: Anders dan Jest, zijn er Mocha, Jasmine, en meer. Elk heeft unieke eigenschappen; kies op basis van je behoeften.
- Implementatiedetails: Tests kunnen naast de code of apart leven. TypeScript-types helpen met automatische aanvulling en bieden extra vertrouwen in tests.

## Zie Ook
- Jest: [Jest Documentatie](https://jestjs.io/docs/getting-started)
- Vergelijking van JS Testraamwerken: [StateOfJS 2022 Enquête](https://2022.stateofjs.com/en-US/libraries/testing/)
