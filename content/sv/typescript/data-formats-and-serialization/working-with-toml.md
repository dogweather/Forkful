---
date: 2024-01-26 04:27:24.753960-07:00
description: "TOML, en f\xF6rkortning f\xF6r Toms Obvious, Minimal Language, \xE4\
  r ett format f\xF6r serialisering av data som liknar JSON eller YAML. Programmerare\
  \ anv\xE4nder det p\xE5\u2026"
lastmod: '2024-03-13T22:44:37.679391-06:00'
model: gpt-4-0125-preview
summary: "TOML, en f\xF6rkortning f\xF6r Toms Obvious, Minimal Language, \xE4r ett\
  \ format f\xF6r serialisering av data som liknar JSON eller YAML."
title: Att arbeta med TOML
weight: 39
---

## Hur man gör:
Först behöver du en TOML-parser. `@iarna/toml` är ett populärt val. Installera det med npm: `npm install @iarna/toml --save`. Så här läser du en TOML-fil och tolkar den till ett JavaScript-objekt:

```typescript
import * as fs from 'fs';
import toml from '@iarna/toml';

const tomlContent = fs.readFileSync('config.toml', 'utf-8');
const parsedData = toml.parse(tomlContent);

console.log(parsedData);
```
Om `config.toml` innehåller:
```
[server]
port = 8080
```
Skulle utdata vara:
```
{ server: { port: 8080 } }
```
Och att skriva till en TOML-fil är lika enkelt:
```typescript
import * as fs from 'fs';
import { stringify } from '@iarna/toml';

const obj = { server: { port: 8080 } };
const tomlString = stringify(obj);
fs.writeFileSync('config.toml', tomlString);
``` 
Att köra denna kod skriver objektet till `config.toml` i TOML-format.

## Djupdykning
TOML skapades av Tom Preston-Werner, medgrundare av GitHub, runt 2013 som ett svar på de begränsningar han uppfattade i andra format som INI eller YAML. Det är utformat för att vara entydigt och enkelt att tolka till datastrukturer, och därför ett favoritval för konfigurationsfiler. Alternativ som JSON saknar kommentarer, medan YAML är mer komplicerat. TOML utmärker sig med sin enkelhet och dess förmåga att tydligt representera komplexa datahierarkier.

Under huven, när du tolkar TOML i TypeScript, konverterar du textuell data till ett strukturerat format som språket kan manipulera. Detta innefattar lexing (att omvandla råtext till tokens) och parsing (bygga en intern datastruktur); `@iarna/toml` hanterar båda sömlöst. Stödet för emojis är en rolig detalj som visar TOML:s användarcentrerade approach.

## Se också
- TOMLs officiella specifikation: https://toml.io/en/
- `@iarna/toml`-paketet: https://www.npmjs.com/package/@iarna/toml
- Jämförelser mellan TOML, YAML och JSON: https://blog.bitsrc.io/choosing-the-right-configuration-file-format-toml-vs-yaml-vs-json-71b5be8968ea
