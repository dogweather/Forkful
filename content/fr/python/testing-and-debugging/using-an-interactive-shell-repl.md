---
title:                "Utilisation d'une console interactive (REPL)"
aliases:
- /fr/python/using-an-interactive-shell-repl/
date:                  2024-01-26T04:17:10.237006-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilisation d'une console interactive (REPL)"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/python/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Un REPL, ou Boucle Lire-Évaluer-Afficher (Read-Eval-Print Loop), est un environnement de programmation qui prend des entrées utilisateur individuelles, les exécute et retourne le résultat à l'utilisateur. Les programmeurs l'utilisent pour des tests rapides, apprendre, déboguer ou effectuer des calculs à la volée.

## Comment faire :
Plongez directement dans le REPL de Python en tapant `python` dans votre ligne de commande. Une fois là, testez des opérations simples ou du code sur plusieurs lignes :

```Python
>>> 1 + 1
2
>>> for i in range(3):
...     print(i)
...
0
1
2
```

Expérimentez avec des fonctions et obtenez un retour immédiat :

```Python
>>> def greet(name):
...     return "Bonjour, " + name + " !"
...
>>> greet("Alice")
'Bonjour, Alice !'
```

Jouez avec des bibliothèques et explorez leurs fonctionnalités en temps réel :

```Python
>>> import math
>>> math.sqrt(16)
4.0
```

Sortez rapidement avec un simple `exit()` ou `Ctrl+D` (parfois `Ctrl+Z` sur Windows).

## Plongée profonde
Le concept d'un REPL n'est pas unique à Python ; il est aussi ancien que Lisp. De nombreux langages offrent cet environnement immédiat et interactif pour une approche pratique du code. Les alternatives au shell Python natif incluent IPython et Jupyter Notebook, qui fournissent une interactivité améliorée, plus de fonctionnalités et une meilleure intégration avec d'autres outils. Le REPL standard de Python est simple, mais il intègre toute la puissance de Python, gérant des objets complexes et des programmes multi-threadés, bien qu'il manque de fonctionnalités comme l'auto-complétion et la coloration syntaxique présentes dans des outils plus avancés.

## Voir également
- [La documentation officielle de Python sur l'interpréteur](https://docs.python.org/3/tutorial/interpreter.html)
- [IPython : Un shell Python avancé](https://ipython.org/)
- [Projet Jupyter](https://jupyter.org/)
