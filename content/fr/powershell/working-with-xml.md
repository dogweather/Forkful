---
title:                "Travailler avec XML"
date:                  2024-01-26T04:34:22.401599-07:00
model:                 gpt-4-0125-preview
simple_title:         "Travailler avec XML"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/powershell/working-with-xml.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Travailler avec XML implique de manipuler et d'accéder à des données structurées en langage XML (eXtensible Markup Language). Les programmeurs travaillent avec XML pour permettre l'interopérabilité avec d'autres systèmes ou pour lire et écrire des fichiers de configuration, des flux de données et d'autres documents structurés courants dans les services web.

## Comment faire :
```PowerShell
# Charger un fichier XML dans une variable
[xml]$xmlContent = Get-Content 'chemin\vers\votre\fichier.xml'

# Accéder aux noeuds XML
$books = $xmlContent.catalog.book
foreach ($book in $books) {
  Write-Output "Titre : $($book.title)"
}

# Créer un nouvel élément XML
$newBook = $xmlContent.CreateElement("book")
$newBook.SetAttribute("id", "bk999")
$xmlContent.DocumentElement.AppendChild($newBook)

# Enregistrer le XML modifié dans un fichier
$xmlContent.Save('chemin\vers\votre\fichier\mis\à\jour.xml')
```
Exemple de sortie :
```
Titre : Programmer avec PowerShell
Titre : Les essentiels de XML
```

## Plongée en profondeur
XML, ou eXtensible Markup Language, existe depuis la fin des années 90 et reste un format largement utilisé pour les données structurées. PowerShell simplifie le travail avec XML par rapport aux méthodes de parsing traditionnelles ; il convertit XML en objets directement, vous permettant d'interagir avec les éléments via une notation par points familière.

Les alternatives à XML incluent JSON, YAML ou des formats de données personnalisés. JSON, par exemple, a gagné en popularité pour sa légèreté et sa facilité d'utilisation avec les technologies web. Cependant, les fonctionnalités étendues de XML telles que les espaces de noms, les schémas et le traitement XSLT en font souvent un meilleur choix pour les documents complexes ou les normes industrielles.

PowerShell utilise les capacités XML du .NET Framework pour sa gestion de XML. Cela signifie qu'il ne s'agit pas seulement d'opérations simples de lecture-écriture ; vous pouvez également travailler avec des schémas XML pour la validation, utiliser XPath pour les requêtes et employer les transformations XSLT, tout cela via PowerShell.

## Voir également
- [Tutoriel XML de W3Schools](https://www.w3schools.com/xml/)
- [XML vs. JSON](https://www.json.org/json-en.html)
