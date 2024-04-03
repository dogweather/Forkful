---
date: 2024-01-20 17:35:48.126759-07:00
description: ("
lastmod: '2024-03-13T22:44:58.009908-06:00'
model: gpt-4-1106-preview
summary: (".
title: "Conversion d'une date en cha\xEEne de caract\xE8res"
weight: 28
---

## How to:
("## Comment faire :")
```Bash
# Afficher la date actuelle au format YYYY-MM-DD
date_actuelle=$(date '+%Y-%m-%d')
echo $date_actuelle
# Exemple de sortie: 2023-04-05

# Convertir un timestamp en date
timestamp=1670000000
date_convertie=$(date -d @$timestamp '+%Y-%m-%d %H:%M:%S')
echo $date_convertie
# Exemple de sortie: 2022-12-03 03:33:20
```

## Deep Dive
("## Exploration approfondie")
`date` est une commande omniprésente sous Unix, existant depuis les premières versions du système. Elle utilise les `format specifiers` (%Y pour l'année, %m pour le mois, etc.) pour modeler l'affichage de la date. 
Alternatives : On peut utiliser `awk`, `perl`, ou des langages de script comme Python pour les besoins plus complexes. La conversion de date en chaîne dépend du fuseau horaire et de la locale ; il est donc important de gérer ces aspects pour éviter les erreurs dans un contexte international.

## See Also
("## À voir également")
- Manual de `date`: `man date` ou [GNU Coreutils - Date](https://www.gnu.org/software/coreutils/manual/html_node/date-invocation.html)
- Bash scripting cheatsheet : [devhints.io/bash](https://devhints.io/bash)
- Tutoriel approfondi sur le formatage de date en Bash : [cyberciti.biz](https://www.cyberciti.biz/faq/linux-unix-formatting-dates-for-display/)
