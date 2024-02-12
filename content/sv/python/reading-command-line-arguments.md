---
title:                "Läsa in kommandoradsargument"
aliases:
- sv/python/reading-command-line-arguments.md
date:                  2024-01-20T17:56:43.544888-07:00
model:                 gpt-4-1106-preview
simple_title:         "Läsa in kommandoradsargument"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/python/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## What & Why? (Vad & Varför?)
Kommandoradsargument låter användare ge input direkt när de kör ett Python-program. Det är viktigt för att skapa flexibla program som kan anpassas vid varje körning utan att ändra koden.

## How to (Hur gör man):
```python
import sys

# Skriv ut alla argument som programmet får
if len(sys.argv) > 1:
    print(f"Argument från kommandoraden: {sys.argv[1:]}")
else:
    print("Inga argument givna.")
```
Kör programmet så här i terminalen:
```bash
python ditt_program.py arg1 arg2
```
Exempel på output:
```
Argument från kommandoraden: ['arg1', 'arg2']
```

## Deep Dive (Djupdykning):
Historiskt sett har kommandoradsargument använts i många typer av programspråk och operativsystem, vilket gör det till en standard för att interagera med program i terminaler eller kommandotolkar. Python's `sys` modulen är den traditionella metoden för att hantera dessa argument. Modulen `argparse` är dock en mer kraftfull och flexibel lösning, som erbjuder parsing av argument och automatisk hjälptext. För specifika uppgifter och stora projekt är det ofta ett bättre val.

För att läsa in argument, tillgängliggör `sys` modulen en lista som heter `argv`. Den håller programmets namn på index 0 och resten är argumenten som följer efter. `argv` står för 'argument values'.

När det gäller implementation, måste man hantera fel som kan uppstå vid inkorrekt input. Programmeraren bör lägga till kontroller för att säkerställa att argumenten som ges är i det förväntade formatet och antalet.

## See Also (Se även):
- Python's officiella dokumentation om `sys` modulen: https://docs.python.org/3/library/sys.html
- Python's officiella dokumentation om `argparse` modulen: https://docs.python.org/3/library/argparse.html
- En bra guide för hur man använder `argparse`: https://realpython.com/command-line-interfaces-python-argparse/
- För ett användarvänligt CLI-gränssnitt kan du kolla in `click` biblioteket: https://click.palletsprojects.com/en/7.x/
