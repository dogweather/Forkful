---
date: 2024-01-20 17:34:43.649713-07:00
description: "Concat\xE9ner des cha\xEEnes, c'est coller des bouts de texte ensemble.\
  \ On le fait pour construire des messages, des chemins de fichiers, ou tout autre\
  \ texte\u2026"
lastmod: '2024-03-13T22:44:58.313506-06:00'
model: gpt-4-1106-preview
summary: "Concat\xE9ner des cha\xEEnes, c'est coller des bouts de texte ensemble."
title: "Concat\xE9nation de cha\xEEnes de caract\xE8res"
weight: 3
---

## How to:
Concaténer des chaînes en Fish est intuitif. Voilà quelques exemples :

```Fish Shell
set string1 "Bonjour, "
set string2 "le monde!"
echo $string1$string2
# Output: Bonjour, le monde!
```

Pour ajouter des espaces ou des éléments statiques, placez-les dans les guillemets :

```Fish Shell
set greeting "Hola, "
set name "Jean"
set exclamation "!"

echo "$greeting$name$exclamation"
# Output: Hola, Jean!
```

Si vos chaînes viennent de commandes, collez-les ainsi :

```Fish Shell
set path (pwd)
set filename "/mon_fichier.txt"
echo $path$filename
# Mettons que vous êtes dans /home/user, le résultat sera :
# Output: /home/user/mon_fichier.txt
```

## Deep Dive
Concaténer des chaînes est une pratique vieille comme la programmation. Historiquement, chaque langage a ses propres méthodes : `+` en Python, `.concat()` en JavaScript, ou simplement juxtaposer en C.

En Fish, pas besoin de fonction compliquée ou d'opérateur spécial ; écrivez simplement les variables l'une à côté de l'autre. Fish gère l'espace entre les mots lorsque vous utilisez des guillemets. C'est clair et naturel, par rapport à des langages où on doit parfois jongler avec différents outils pour obtenir le résultat escompté.

D'autres shells, comme Bash, utilisent des syntaxes plus cryptiques comme l'utilisation de `${var}`. Fish, fidèle à sa philosophie de simplicité, rend cette tâche transparente.

## See Also
Pour plus de détails sur la manipulation de chaînes en Fish, consultez :
- La documentation officielle de Fish sur les variables : [https://fishshell.com/docs/current/index.html#variables](https://fishshell.com/docs/current/index.html#variables)
- Un tutoriel Fish complet pour débutants : [https://fishshell.com/docs/current/tutorial.html](https://fishshell.com/docs/current/tutorial.html)
- Questions fréquentes (FAQ) de Fish, incluant des astuces sur les chaînes : [https://fishshell.com/docs/current/faq.html](https://fishshell.com/docs/current/faq.html)
