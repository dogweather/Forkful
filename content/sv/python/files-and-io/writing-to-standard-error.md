---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:24.297928-07:00
description: "Att skriva till standardfel i Python handlar om att rikta ditt programs\
  \ felmeddelanden eller diagnostik till felstr\xF6mmen (`stderr`), separat fr\xE5\
  n\u2026"
lastmod: '2024-03-13T22:44:37.499221-06:00'
model: gpt-4-0125-preview
summary: "Att skriva till standardfel i Python handlar om att rikta ditt programs\
  \ felmeddelanden eller diagnostik till felstr\xF6mmen (`stderr`), separat fr\xE5\
  n standardutmatningen (`stdout`)."
title: Skriva till standardfel
weight: 25
---

## Hur gör man:


### Använda `sys.stderr`
Pythons inbyggda `sys`-modul tillåter explicit skrivning till `stderr`. Detta tillvägagångssätt är okomplicerat för enkla felmeddelanden eller diagnostik.

```python
import sys

sys.stderr.write('Fel: Något gick fel.\n')
```
Exempel på utdata (till stderr):
```
Fel: Något gick fel.
```

### Använda `print`-funktionen
Pythons `print`-funktion kan omdirigera sin utskrift till `stderr` genom att specificera `file`-parametern. Denna metod är användbar för att utnyttja `print`:s användarvänlighet samtidigt som man hanterar felmeddelanden.
```python
from sys import stderr

print('Fel: Fel i modulen.', file=stderr)
```
Exempel på utdata (till stderr):
```
Fel: Fel i modulen.
```

### Använda `logging`-modulen
För en mer omfattande lösning kan Pythons `logging`-modul rikta meddelanden till `stderr` och mycket mer, såsom att skriva till en fil eller anpassa meddelandeformat. Denna metod är bäst för applikationer som kräver olika nivåer av loggning, meddelandeformatering eller destinationer.
```python
import logging

logging.basicConfig(level=logging.WARNING)
logger = logging.getLogger(__name__)

logger.error('Fel: Databasanslutning misslyckades.')
```
Exempel på utdata (till stderr):
```
ERROR:__main__:Fel: Databasanslutning misslyckades.
```

### Tredjepartsbibliotek: `loguru`
`loguru` är ett populärt tredjepartsbibliotek som förenklar loggning i Python-applikationer. Det dirigerar automatiskt fel till `stderr`, bland andra funktioner.

För att använda `loguru`, installera det först via pip:
```shell
pip install loguru
```

Inkorporera sedan det i ditt Python-skript enligt följande:
```python
from loguru import logger

logger.error('Fel: Misslyckades med att öppna fil.')
```
Exempel på utdata (till stderr):
```
2023-04-05 12:00:00.000 | ERROR    | __main__:<module>:6 - Fel: Misslyckades med att öppna fil.
```
