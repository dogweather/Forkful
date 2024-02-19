---
aliases:
- /it/python/working-with-xml/
date: 2024-01-26 04:34:43.300468-07:00
description: "\"Lavorare con XML\" si riferisce al processo di lettura, creazione\
  \ e modifica dei file XML (eXtensible Markup Language) utilizzando la programmazione.\
  \ I\u2026"
lastmod: 2024-02-18 23:08:55.544532
model: gpt-4-0125-preview
summary: "\"Lavorare con XML\" si riferisce al processo di lettura, creazione e modifica\
  \ dei file XML (eXtensible Markup Language) utilizzando la programmazione. I\u2026"
title: Lavorare con XML
---

{{< edit_this_page >}}

## Cosa e Perché?
"Lavorare con XML" si riferisce al processo di lettura, creazione e modifica dei file XML (eXtensible Markup Language) utilizzando la programmazione. I programmatori lo fanno perché XML è ampiamente utilizzato per lo scambio di dati a causa della sua natura indipendente dalla piattaforma e del formato auto-descrittivo.

## Come fare:
Il modulo `xml.etree.ElementTree` di Python offre strumenti per lavorare con XML.

Analizzare un documento XML:
```python
import xml.etree.ElementTree as ET

xml_data = """<?xml version="1.0"?>
<library>
    <book>
        <title>Learning Python</title>
        <author>Mark Lutz</author>
    </book>
    <book>
        <title>Programming Python</title>
        <author>Mark Lutz</author>
    </book>
</library>
"""

root = ET.fromstring(xml_data)
for book in root.findall('book'):
    title = book.find('title').text
    author = book.find('author').text
    print(f'Titolo: {title}, Autore: {author}')
```
Esempio di output:
```
Titolo: Learning Python, Autore: Mark Lutz
Titolo: Programming Python, Autore: Mark Lutz
```

Creare un documento XML:
```python
library = ET.Element('library')
book = ET.SubElement(library, 'book')
title = ET.SubElement(book, 'title')
title.text = 'Automate the Boring Stuff with Python'
author = ET.SubElement(book, 'author')
author.text = 'Al Sweigart'

tree = ET.ElementTree(library)
tree.write('library.xml')
```

## Approfondimento:
XML è stato creato alla fine degli anni '90 come sottoinsieme semplificato di SGML per facilitare la condivisione di dati online. Nonostante la crescente popolarità di JSON per i dati web, XML rimane vitale in molte imprese, configurazioni e servizi web (SOAP, RSS).

Alternative a `xml.etree.ElementTree` includono `lxml` e `minidom`. `lxml` è più veloce e ricco di funzionalità, mentre `minidom` offre un'interfaccia XML più "simile a DOM". Nella scelta, considerare la facilità di uso, le prestazioni e i requisiti specifici delle funzionalità.

Sotto il cofano, `ElementTree` opera su un modello ad albero di elementi, dove ogni componente del file XML è un nodo in un albero. Ciò consente espressioni e ricerche di percorsi semplici, rendendo più facile navigare e manipolare la struttura dei dati XML.

## Vedere anche:
- Modulo Python `xml.etree.ElementTree`: https://docs.python.org/3/library/xml.etree.elementtree.html
- `lxml`: https://lxml.de/
- Tutorial XML di W3Schools: https://www.w3schools.com/xml/
- Specifica XML: https://www.w3.org/XML/
