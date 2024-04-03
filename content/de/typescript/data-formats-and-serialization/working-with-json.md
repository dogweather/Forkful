---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:39.960249-07:00
description: "Die Arbeit mit JSON (JavaScript Object Notation) umfasst das Parsen\
  \ von JSON-Daten zu einem in TypeScript nutzbaren Format und umgekehrt. Programmierer\u2026"
lastmod: '2024-03-13T22:44:53.651640-06:00'
model: gpt-4-0125-preview
summary: Die Arbeit mit JSON (JavaScript Object Notation) umfasst das Parsen von JSON-Daten
  zu einem in TypeScript nutzbaren Format und umgekehrt.
title: Arbeiten mit JSON
weight: 38
---

## Wie:


### Parsen von JSON zu einem TypeScript-Objekt
Um einen JSON-String in ein TypeScript-Objekt umzuwandeln, verwenden Sie die Methode `JSON.parse()`. Dies ist nützlich, wenn Sie JSON-Daten von einem Webserver erhalten oder eine JSON-Datei lesen.

```typescript
const jsonStr = '{"name": "John Doe", "age": 30}';
const obj = JSON.parse(jsonStr);

console.log(obj.name); // Ausgabe: John Doe
```

### Umwandlung eines TypeScript-Objekts in einen JSON-String
Um ein TypeScript-Objekt in einen JSON-String zu konvertieren, verwenden Sie die Methode `JSON.stringify()`. Dies ist besonders nützlich, wenn Sie Daten an einen Webserver senden müssen.

```typescript
const person = {
  name: "Jane Doe",
  age: 25,
};

const jsonStr = JSON.stringify(person);

console.log(jsonStr); // Ausgabe: {"name":"Jane Doe","age":25}
```

### Arbeit mit Interfaces
Sie können TypeScript-Interfaces definieren, um nahtlos mit JSON-Daten zu arbeiten, indem Sie die Struktur Ihrer Objekte sicherstellen.

```typescript
interface Person {
  name: string;
  age: number;
}

const jsonStr = '{"name": "Alex", "age": 28}';
const person: Person = JSON.parse(jsonStr);

console.log(person.age); // Ausgabe: 28
```

### Verwendung beliebter Drittanbieterbibliotheken
Für komplexere Szenarien wie Schemaüberprüfung oder Transformation können Sie auf Bibliotheken wie `class-transformer` oder `AJV` (Another JSON Schema Validator) zurückgreifen.

#### class-transformer
Diese Bibliothek kann einfache Objekte in Klasseninstanzen und umgekehrt umwandeln, was für Typüberprüfung und -manipulation nützlich ist.

```typescript
import "reflect-metadata";
import { plainToClass } from "class-transformer";
import { Person } from "./person";

const jsonStr = '{"name": "Mia", "age": 22}';
const person = plainToClass(Person, JSON.parse(jsonStr));

console.log(person instanceof Person); // Ausgabe: true
console.log(person.name); // Ausgabe: Mia
```

#### AJV
AJV ist eine Bibliothek, die eine schnelle JSON-Schemavalidierung ermöglicht. Das bedeutet, Sie können JSON-Objekte gegen vordefinierte Schemata validieren.

```typescript
import Ajv from "ajv";

const ajv = new Ajv();

const schema = {
  type: "object",
  properties: {
    name: { type: "string" },
    age: { type: "number" },
  },
  required: ["name", "age"],
  additionalProperties: false,
};

const validate = ajv.compile(schema);
const valid = validate({ name: "Tom", age: 24 });

console.log(valid); // Ausgabe: true
if (!valid) console.log(validate.errors);
```

Mit diesen Werkzeugen und Techniken können Sie JSON-Daten in Ihren TypeScript-Anwendungen effizient handhaben, die Datenintegrität gewährleisten und das leistungsfähige Typsystem von TypeScript nutzen.
