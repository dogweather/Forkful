---
date: 2024-01-20 17:37:12.590511-07:00
description: "Konvertering av dato til streng handler om \xE5 endre et datoobjekt\
  \ til en tekstrepresentasjon. Dette er nyttig for \xE5 vise datoer lesevennlig for\
  \ brukere\u2026"
lastmod: '2024-03-13T22:44:40.372703-06:00'
model: gpt-4-1106-preview
summary: "Konvertering av dato til streng handler om \xE5 endre et datoobjekt til\
  \ en tekstrepresentasjon."
title: Konvertere en dato til en streng
weight: 28
---

## Hvordan gjøre det:
```Python
from datetime import datetime

# Nåværende dato og tid
naa = datetime.now()

# Konverter til streng
dato_streng = naa.strftime("%d.%m.%Y %H:%M")
print(dato_streng)
```
Eksempelutskrift:
```
24.03.2023 15:45
```

## Dypdykk
Historisk har datoer og tidspunkt i programmering ofte vært representert ved tall eller komplekse strukturer, som i C's `tm` struktur. Python tilbyr derimot `datetime`-modulen, noe som forenkler arbeidet med datoer og tider.

Det finnes flere måter å konvertere datoer til strenger på i Python. `strftime()` er den vanligste funksjonen og står for "string format time". Den lar deg definere hvordan dato og tid skal formateres med spesifikke koder, som `%d` for dag og `%m` for måned. Andre metoder inkluderer å bruke ISO-format ved `isoformat()` eller konvertere til timestamp og så til streng.

En ting å vokte seg for er tidsonebehandling – `datetime.now()` uten argument gir tiden i lokal tidssone. Ønsker man å sikre universell tid, kan `datetime.utcnow()` brukes.

## Se også
- Python `datetime`-modulen: https://docs.python.org/3/library/datetime.html
- strftime() og strptime() adferd: https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior
- Tidssoner i Python med pytz: https://pypi.org/project/pytz/
