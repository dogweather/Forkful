---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:41.234141-07:00
description: "JSON (JavaScript Object Notation) is een alomtegenwoordig data-uitwisselingsformaat\
  \ op het web. Programmeurs gebruiken JSON om gemakkelijk gegevens tussen\u2026"
lastmod: '2024-03-13T22:44:50.397597-06:00'
model: gpt-4-0125-preview
summary: JSON (JavaScript Object Notation) is een alomtegenwoordig data-uitwisselingsformaat
  op het web.
title: Werken met JSON
weight: 38
---

## Hoe te:
Werken met JSON in Python vereist de `json` module. Hier is een snelle doorloop:

### Parsing JSON (`json.loads`):
```Python
import json

# Stel je voor dat je JSON van een API hebt gekregen
json_string = '{"naam": "Alice", "leeftijd": 30, "stad": "Wonderland"}'

# Parse de JSON-string naar een Python woordenboek
persoon = json.loads(json_string)

print(persoon)
```

### Voorbeelduitvoer:
```Python
{'naam': 'Alice', 'leeftijd': 30, 'stad': 'Wonderland'}
```

### Genereren van JSON (`json.dumps`):
```Python
import json

# Python woordenboek
persoon_dict = {'naam': 'Alice', 'leeftijd': 30, 'stad': 'Wonderland'}

# Converteer het woordenboek naar een JSON-geformatteerde string
persoon_json = json.dumps(persoon_dict)

print(persoon_json)
```

### Genereren van JSON (`json.dumps`):
```Python
import json

# Python woordenboek
persoon_dict = {'naam': 'Alice', 'leeftijd': 30, 'stad': 'Wonderland'}

# Converteer het woordenboek naar een JSON-geformatteerde string
persoon_json = json.dumps(persoon_dict)

print(persoon_json)
```

## Diepere Duik
JSON werd begin jaren 2000 voorgesteld door Douglas Crockford als een deel van de JavaScript-taal, maar werd snel aangenomen over de talen heen vanwege het lichtgewicht formaat. Alternatieven voor JSON zijn onder andere XML en YAML, maar JSON wint qua minimalisme en snelheid. Direct in Python serialiseert JSON naar strings en deserialiseert naar woordenboeken of lijsten, waardoor het gemakkelijk programmeerbaar is. Merk op dat hoewel JSON lijkt op een Python-woordenboek, ze niet hetzelfde zijn - je kunt Python-specifieke objecten en typen niet gebruiken in JSON.

## Zie Ook
- Officiële JSON-website: [json.org](https://www.json.org)
- Documentatie van Python's JSON-module: [Python JSON](https://docs.python.org/3/library/json.html)
- Vergelijking tussen JSON en XML: [JSON vs XML](https://www.w3schools.com/js/js_json_xml.asp)
- Python 3.x Documentatie: [python.org](https://www.python.org/doc/)
