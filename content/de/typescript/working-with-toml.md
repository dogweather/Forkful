---
title:                "Arbeiten mit TOML"
aliases:
- de/typescript/working-with-toml.md
date:                  2024-01-26T04:27:04.148803-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeiten mit TOML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/typescript/working-with-toml.md"
---

{{< edit_this_page >}}

## Was & Warum?
TOML, die Abkürzung für Toms Offensichtliche, Minimale Sprache, ist ein Daten-Serialisierungsformat ähnlich zu JSON oder YAML. Programmierer nutzen es wegen seiner menschlichen Lesbarkeit und der unkomplizierten Zuordnung zu Datentypen, was es zu einer ersten Wahl für Konfigurationsdateien und Datenaustausch macht.

## Wie geht das:
Zuerst benötigst du einen TOML-Parser. `@iarna/toml` ist eine beliebte Wahl. Installiere es mit npm: `npm install @iarna/toml --save`. So liest du eine TOML-Datei und parst sie zu einem JavaScript-Objekt:

```typescript
import * as fs from 'fs';
import toml from '@iarna/toml';

const tomlContent = fs.readFileSync('config.toml', 'utf-8');
const parsedData = toml.parse(tomlContent);

console.log(parsedData);
```
Wenn `config.toml` beinhaltet:
```
[server]
port = 8080
```
Wäre die Ausgabe:
```
{ server: { port: 8080 } }
```
Und, in eine TOML-Datei zu schreiben ist genauso unkompliziert:
```typescript
import * as fs from 'fs';
import { stringify } from '@iarna/toml';

const obj = { server: { port: 8080 } };
const tomlString = stringify(obj);
fs.writeFileSync('config.toml', tomlString);
``` 
Dieser Code schreibt das Objekt im TOML-Format in `config.toml`.

## Tiefere Einblicke
TOML wurde von Tom Preston-Werner, dem Mitbegründer von GitHub, um 2013 als Antwort auf die von ihm wahrgenommenen Einschränkungen anderer Formate wie INI oder YAML geschaffen. Es ist darauf ausgelegt, eindeutig und leicht in Datenstrukturen zu parsen zu sein, daher ein Favorit für Konfigurationsdateien. Alternativen wie JSON fehlen Kommentare, während YAML komplexer ist. TOML glänzt in seiner Einfachheit und seiner Fähigkeit, komplexe Datenhierarchien klar darzustellen.

Unter der Haube, wenn du TOML in TypeScript parst, konvertierst du textuelle Daten in ein strukturiertes Format, das die Sprache manipulieren kann. Dies beinhaltet Lexing (rohen Text in Token umwandeln) und Parsen (eine interne Datenstruktur aufbauen); `@iarna/toml` handhabt beides nahtlos. Die Emoji-Unterstützung ist eine lustige Note, die TOMLs benutzerzentrierten Ansatz zeigt.

## Siehe auch
- Offizielle TOML-Spezifikation: https://toml.io/en/
- `@iarna/toml` Paket: https://www.npmjs.com/package/@iarna/toml
- Vergleiche zwischen TOML, YAML und JSON: https://blog.bitsrc.io/choosing-the-right-configuration-file-format-toml-vs-yaml-vs-json-71b5be8968ea
