---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:39.581886-07:00
description: "Das Parsen von HTML beinhaltet die Analyse des HTML-Codes einer Webseite,\
  \ um spezifische Informationen oder Elemente zu extrahieren. Es ist eine g\xE4ngige\u2026"
lastmod: '2024-03-13T22:44:53.376119-06:00'
model: gpt-4-0125-preview
summary: Das Parsen von HTML beinhaltet die Analyse des HTML-Codes einer Webseite,
  um spezifische Informationen oder Elemente zu extrahieren.
title: HTML parsen
weight: 43
---

## Wie geht das:
Python bietet leistungsstarke Bibliotheken wie BeautifulSoup und requests für Web Scraping und HTML-Parsing. Um zu beginnen, müssen Sie diese Bibliotheken installieren, falls Sie dies noch nicht getan haben:

```bash
pip install beautifulsoup4 requests
```

Hier ist ein einfaches Beispiel, das `requests` verwendet, um den HTML-Inhalt einer Webseite abzurufen, und `BeautifulSoup`, um ihn zu parsen:

```python
import requests
from bs4 import BeautifulSoup

# Den Inhalt einer Webseite abrufen
URL = 'https://example.com'
page = requests.get(URL)

# Den HTML-Inhalt parsen
soup = BeautifulSoup(page.content, 'html.parser')

# Beispiel für das Extrahieren des Titels der Webseite
title = soup.find('title').text
print(f'Webseitentitel: {title}')
```

**Beispielausgabe**:
```
Webseitentitel: Beispiel-Domain
```

Für komplexere Anfragen, wie das Extrahieren aller Links von einer Webseite, können Sie die verschiedenen Methoden von BeautifulSoup zum Navigieren und Durchsuchen des Parse-Baums verwenden:

```python
# Alle Links innerhalb von <a>-Tags extrahieren
links = soup.find_all('a')

for link in links:
    href = link.get('href')
    print(href)
```

**Beispielausgabe**:
```
https://www.iana.org/domains/example
```

Die Flexibilität von BeautifulSoup erlaubt es Ihnen, Ihre Suche nach den exakt benötigten Daten anzupassen, was das HTML-Parsing zu einem mächtigen Werkzeug für Programmierer macht, die mit Webinhalten arbeiten.
