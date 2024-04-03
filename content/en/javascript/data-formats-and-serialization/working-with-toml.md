---
date: 2024-01-25 03:39:59.423234-07:00
description: "TOML, short for Tom's Obvious, Minimal Language, defines how to structure\
  \ config files. Programmers work with TOML because it's easy to read, write, and\u2026"
lastmod: '2024-03-13T22:45:00.455224-06:00'
model: gpt-4-1106-preview
summary: TOML, short for Tom's Obvious, Minimal Language, defines how to structure
  config files.
title: Working with TOML
weight: 39
---

## How to:
To work with TOML in JavaScript, you'll need a parser like `@iarna/toml`. First, install it: `npm install @iarna/toml`. Then, parse a TOML string to a JavaScript object or stringify a JavaScript object to TOML format.

```javascript
const toml = require('@iarna/toml');

// Parse TOML string to JS object
const tomlStr = `
title = "TOML Example"

[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
`;

const parsedData = toml.parse(tomlStr);
console.log(parsedData);

// Convert JS object to TOML string
const jsObject = {
  title: "TOML Example",
  database: {
    server: "192.168.1.1",
    ports: [8001, 8001, 8002]
  }
};

const tomlString = toml.stringify(jsObject);
console.log(tomlString);
```

## Deep Dive
TOML was first released in 2013 by Tom Preston-Werner, a co-founder of GitHub. It was designed to supersede other formats, like INI, by being more standardized and easier to parse. JSON and YAML are alternatives but can be too complex or too flexible. TOML's advantage is in static configuration where a simple, clear format is preferred. Its design allows for straightforward mapping into a hash table, with keys and values corresponding to property names and their values. For wider adoption, you might need to integrate tools that can convert between TOML and other formats due to varying ecosystem support.

## See Also
- The official TOML GitHub repository: https://github.com/toml-lang/toml
- TOML vs. YAML vs. JSON comparison: https://gist.github.com/oconnor663/9aeb4ed56394cb013a20
- npm `@iarna/toml` package: https://www.npmjs.com/package/@iarna/toml
