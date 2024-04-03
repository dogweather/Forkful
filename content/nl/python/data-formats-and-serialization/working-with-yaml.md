---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:11:46.945981-07:00
description: "Werken met YAML betekent het parseren en genereren van YAML (Yet Another\
  \ Markup Language) documenten in Python. Programmeurs doen dit om\u2026"
lastmod: '2024-03-13T22:44:50.396678-06:00'
model: gpt-4-0125-preview
summary: Werken met YAML betekent het parseren en genereren van YAML (Yet Another
  Markup Language) documenten in Python.
title: Werken met YAML
weight: 41
---

## Hoe:
Om met YAML in Python te werken, heb je `pyyaml` nodig. Installeer het met:

```Python
pip install pyyaml
```

Lees een YAML-bestand:

```Python
import yaml

met open('config.yaml', 'r') als stream:
    proberen:
        config = yaml.safe_load(stream)
        print(config)
    behalve yaml.YAMLError als exc:
        print(exc)
```

Schrijf naar een YAML-bestand:

```Python
config = {'database': {'host': 'localhost', 'poort': 3306}}

met open('config.yaml', 'w') als bestand:
    yaml.dump(config, bestand, default_flow_style=False)
```

Zo ziet `config.yaml` eruit:

```yaml
database:
  host: localhost
  poort: 3306
```

## Diepgaand
YAML werd gelanceerd in 2001 als een gebruiksvriendelijke gegevensserialisatiestandaard voor alle programmeertalen. JSON en XML zijn alternatieven, maar de focus van YAML op leesbaarheid is een opvallend kenmerk. Bij het parseren is `safe_load` cruciaal om willekeurige code-uitvoering te voorkomen vanwege onveilige YAML-inhoud. `default_flow_style=False` houdt de output niet JSON-achtig, waardoor de leesbaarheid van YAML behouden blijft.

## Zie Ook
- Officiële PyYAML Documentatie: https://pyyaml.org/wiki/PyYAMLDocumentation
- YAML Specificatie: https://yaml.org/spec/1.2/spec.html
- Vergelijking tussen JSON en YAML: https://csrc.nist.gov/csrc/media/projects/cryptographic-standards-and-guidelines/documents/examples/data-serialization.pdf
