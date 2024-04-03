---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:06:38.884079-07:00
description: "En programmation Bash, v\xE9rifier si un r\xE9pertoire existe est un\
  \ m\xE9canisme de contr\xF4le essentiel utilis\xE9 pour v\xE9rifier la pr\xE9sence\
  \ d'un r\xE9pertoire avant\u2026"
lastmod: '2024-03-13T22:44:58.012847-06:00'
model: gpt-4-0125-preview
summary: "En programmation Bash, v\xE9rifier si un r\xE9pertoire existe est un m\xE9\
  canisme de contr\xF4le essentiel utilis\xE9 pour v\xE9rifier la pr\xE9sence d'un\
  \ r\xE9pertoire avant d'effectuer des op\xE9rations sur des fichiers."
title: "V\xE9rifier si un r\xE9pertoire existe"
weight: 20
---

## Comment faire :
Au cœur de Bash, vous pouvez vérifier l'existence d'un répertoire en utilisant des instructions conditionnelles et l'opérateur `-d`. Voici un exemple simple qui montre comment effectuer cette vérification.

```bash
if [ -d "/chemin/vers/repertoire" ]; then
    echo "Le répertoire existe."
else
    echo "Le répertoire n'existe pas."
fi
```

Sortie d'exemple (si le répertoire existe) :
```
Le répertoire existe.
```

Sortie d'exemple (si le répertoire n'existe pas) :
```
Le répertoire n'existe pas.
```

Pour des scripts plus complexes, il est courant de combiner la vérification avec d'autres opérations, comme créer le répertoire s'il n'existe pas :

```bash
REP="/chemin/vers/repertoire"
if [ -d "$REP" ]; then
    echo "$REP existe."
else
    echo "$REP n'existe pas. Création en cours..."
    mkdir -p "$REP"
    echo "$REP créé."
fi
```

Sortie d'exemple (si le répertoire n'existe pas puis est créé) :
```
/chemin/vers/repertoire n'existe pas. Création en cours...
/chemin/vers/repertoire créé.
```

Bien que Bash lui-même fournisse des outils robustes pour de telles vérifications, il n'existe pas de bibliothèques tierces populaires spécifiquement pour cette tâche, car les commandes Bash natives sont tout à fait capables et efficaces pour la validation de la présence de répertoires.
