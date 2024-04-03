---
date: 2024-01-26 04:23:45.447274-07:00
description: "TOML, eine Abk\xFCrzung f\xFCr Toms Offensichtliche, Minimale Sprache,\
  \ definiert, wie Konfigurationsdateien strukturiert werden sollen. Programmierer\
  \ arbeiten\u2026"
lastmod: '2024-03-13T22:44:54.289719-06:00'
model: gpt-4-0125-preview
summary: "TOML, eine Abk\xFCrzung f\xFCr Toms Offensichtliche, Minimale Sprache, definiert,\
  \ wie Konfigurationsdateien strukturiert werden sollen."
title: Arbeiten mit TOML
weight: 39
---

## Wie man vorgeht:
Um mit TOML in JavaScript zu arbeiten, benötigen Sie einen Parser wie `@iarna/toml`. Installieren Sie es zuerst: `npm install @iarna/toml`. Anschließend können Sie einen TOML-String in ein JavaScript-Objekt umwandeln oder ein JavaScript-Objekt in das TOML-Format umwandeln.

```javascript
const toml = require('@iarna/toml');

// TOML-String in JS-Objekt umwandeln
const tomlStr = `
title = "TOML-Beispiel"

[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
`;

const parsedData = toml.parse(tomlStr);
console.log(parsedData);

// JS-Objekt in TOML-String umwandeln
const jsObject = {
  title: "TOML-Beispiel",
  database: {
    server: "192.168.1.1",
    ports: [8001, 8001, 8002]
  }
};

const tomlString = toml.stringify(jsObject);
console.log(tomlString);
```

## Vertiefung
TOML wurde erstmals 2013 von Tom Preston-Werner, einem Mitbegründer von GitHub, veröffentlicht. Es wurde entworfen, um andere Formate, wie INI, durch einen standardisierten und leichter zu parsenden Aufbau zu ersetzen. JSON und YAML sind Alternativen, können aber zu komplex oder zu flexibel sein. Der Vorteil von TOML liegt in statischen Konfigurationen, wo ein einfaches, klares Format bevorzugt wird. Sein Entwurf erlaubt eine unkomplizierte Abbildung in eine Hashtabelle, wobei Schlüssel und Werte den Eigenschaftsnamen und ihren Werten entsprechen. Für eine breitere Akzeptanz müssen möglicherweise Tools integriert werden, die eine Umwandlung zwischen TOML und anderen Formaten ermöglichen, aufgrund unterschiedlicher Unterstützung im Ökosystem.

## Siehe auch
- Das offizielle TOML GitHub-Repository: https://github.com/toml-lang/toml
- Vergleich TOML vs. YAML vs. JSON: https://gist.github.com/oconnor663/9aeb4ed56394cb013a20
- npm-Paket `@iarna/toml`: https://www.npmjs.com/package/@iarna/toml
