---
aliases:
- /no/javascript/writing-tests/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:31:14.242754-07:00
description: "\xC5 skrive tester i JavaScript refererer til praksisen med \xE5 lage\
  \ automatiserte skript som kj\xF8rer koden din for \xE5 sikre at den oppf\xF8rer\
  \ seg som forventet,\u2026"
lastmod: 2024-02-18 23:08:54.312256
model: gpt-4-0125-preview
summary: "\xC5 skrive tester i JavaScript refererer til praksisen med \xE5 lage automatiserte\
  \ skript som kj\xF8rer koden din for \xE5 sikre at den oppf\xF8rer seg som forventet,\u2026"
title: Skrive tester
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Å skrive tester i JavaScript refererer til praksisen med å lage automatiserte skript som kjører koden din for å sikre at den oppfører seg som forventet, noe som kan forbedre påliteligheten og vedlikeholdbarheten til applikasjonene dine betydelig. Programmerere gjør dette for å fange opp feil tidlig, lette omstrukturering av kode og sikre at nye funksjoner ikke bryter eksisterende funksjonalitet.

## Hvordan:

### Innfødt tilnærming (bruker Jest)

Jest er et populært testrammeverk som gir et vennlig API for å skrive enhetstester i JavaScript. Det krever minimal konfigurasjon og kommer med funksjoner som mock-funksjoner, timere og øyeblikksbilde-testing.

1. **Installasjon**:

```bash
npm install --save-dev jest
```

2. **Skrive en enkel test**:

Opprett en fil med navnet `sum.test.js`:

```javascript
const sum = require('./sum'); // Anta at denne funksjonen simpelthen legger sammen to tall

test('legger 1 + 2 til å bli 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

3. **Kjøre testen din**:

```bash
npx jest
```

**Eksempel på utdata:**

```plaintext
PASS  ./sum.test.js
✓ legger 1 + 2 til å bli 3 (5ms)
```

### Testing av asynkron kode

Jest gjør det enkelt å teste lovnader og async/await-syntaks:

```javascript
// asyncSum.js
async function asyncSum(a, b) {
  return Promise.resolve(a + b);
}

// asyncSum.test.js
test('asynkron addisjon fungerer', async () => {
  await expect(asyncSum(1, 2)).resolves.toBe(3);
});
```

### Bruke tredjepartsbiblioteker (Mocha & Chai)

Mocha er et annet populært testrammeverk, ofte brukt med påstandsbiblioteket Chai for mer uttrykksfulle tester.

1. **Installasjon**:

```bash
npm install --save-dev mocha chai
```

2. **Skrive en test med Mocha og Chai**:

Opprett `calculate.test.js`:

```javascript
const chai = require('chai');
const expect = chai.expect;

const calculate = require('./calculate'); // En enkel beregningsmodul

describe('Calculate', function() {
  it('skal summere to verdier', function() {
    expect(calculate.sum(5, 2)).to.equal(7);
  });
});
```

3. **Kjøre testene dine med Mocha**:

Legg til et skript i din `package.json`:

```json
"scripts": {
  "test": "mocha"
}
```

Deretter utfør:

```bash
npm test
```

**Eksempel på utdata:**

```plaintext
  Calculate
    ✓ skal summere to verdier

  1 passing (8ms)
```

Disse eksemplene illustrerer grunnleggende testskriving og utførelse i JavaScript. Å adoptere et testrammeverk som Jest eller Mocha med Chai, kan gi et solid fundament for robust applikasjonstesting, noe som hjelper til med å sikre at koden din fungerer som tiltenkt gjennom oppdateringer og omstruktureringer.
