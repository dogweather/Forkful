---
title:                "Interpolering av en streng"
aliases:
- no/python/interpolating-a-string.md
date:                  2024-01-28T21:23:40.105231-07:00
model:                 gpt-4-0125-preview
simple_title:         "Interpolering av en streng"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/python/interpolating-a-string.md"
changelog:
  - 2024-01-28, dogweather, reviewed
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Strenginterpolasjon er metoden for å bygge inn uttrykk i strenglitteraler. Programmerere bruker det for å dynamisk sette inn verdier i strenger, noe som gjør koden mer lesbar og ryddigere enn tradisjonell strengkonkatenering.

## Hvordan:
I Python 3.6 og nyere, kan du interpolere strenger ved å bruke f-strenger. Slik gjør du:

```Python
name = 'Alice'
age = 30
greeting = f"Hei, {name}. Du er {age} år gammel."

print(greeting)
```

Output:
```
Hei, Alice. Du er 30 år gammel.
```

Du kan også bruke uttrykk inne i krøllparentesene:

```Python
a = 5
b = 10
info = f"Fem pluss ti er {a + b}, ikke {2 * (a + b)}."

print(info)
```

Output:
```
Fem pluss ti er 15, ikke 30.
```

## Dypdykk
Før Python 3.6, var `.format()` metoden å bruke for strenginterpolasjon:

```Python
name = 'Bob'
age = 25
greeting = "Hei, {}. Du er {} år gammel.".format(name, age)

print(greeting)
```

Gammeldags Python (versjoner < 2.6) brukte `%`-operatoren for interpolasjon, som er mindre intuitiv og kan bli rotete med flere variabler:

```Python
name = 'Carol'
age = 35
greeting = "Hei, %s. Du er %d år gammel." % (name, age)

print(greeting)
```

Bortsett fra renere syntaks, er f-strenger raskere fordi de blir evaluert i kjøretid og deretter konvertert direkte til en effektiv strengformatoperasjon. `.format()`-metoden og `%`-operatoren involverer flere trinn og er tregere.

## Se også
- [PEP 498 – Literal String Interpolation](https://www.python.org/dev/peps/pep-0498/) for offisiell dokumentasjon om f-strenger.
- [Python f-strenger](https://realpython.com/python-f-strings/) av Real Python for en veiledning om bruk av f-strenger.
- [.format() Metoden](https://docs.python.org/3/library/stdtypes.html#str.format) i Python-dokumentasjonen for å forstå den eldre `.format()`-metoden for strengformatering.
