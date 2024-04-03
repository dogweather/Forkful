---
date: 2024-01-20 17:36:11.451936-07:00
description: "\"Quoi et pourquoi ?\" Transformer une date en cha\xEEne de caract\xE8\
  res, c'est convertir l'information temporelle en texte. On le fait pour l'afficher,\
  \ la\u2026"
lastmod: '2024-03-13T22:44:58.337117-06:00'
model: gpt-4-1106-preview
summary: '"Quoi et pourquoi .'
title: "Conversion d'une date en cha\xEEne de caract\xE8res"
weight: 28
---

## How to:
"Comment faire :" Pour convertir une date en chaîne dans Fish, on utilise souvent `date`. Exemple simple :

```Fish Shell
set date_string (date "+%Y-%m-%d")
echo $date_string
```

Sortie :
```
2023-03-15
```

## Deep Dive
"Plongée en profondeur" : Historiquement, `date` vient d'Unix. Fish, moderne et scriptable, facilite la manipulation de dates. Contrairement à d'autres shells, Fish ne requiert pas de mots clefs comme `export` pour définir des variables. Les alternatives incluent l'utilisation de commandes Python ou AWK, mais `date` reste simple et directe. Les formats sont flexibles - `%Y` pour l'année, `%m` pour le mois, `%d` pour le jour, et il y en a bien d'autres.

## See Also
"Voir aussi" :
- Documentation Fish Shell : [link]
- Commande `date` : [link]
- Formatage des dates POSIX : [link]
