---
title:                "Affichage des sorties de débogage"
date:                  2024-01-20T17:52:19.451321-07:00
model:                 gpt-4-1106-preview
simple_title:         "Affichage des sorties de débogage"
programming_language: "Fish Shell"
category:             "Fish Shell"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/fish-shell/printing-debug-output.md"
---

{{< edit_this_page >}}

## What & Why?
L'affichage de sorties de débogage, c'est exposer les entrailles de votre code – voir ce qu'il se passe en temps réel. Les développeurs le font pour traquer les bugs plus efficacement.

## How to:
Pour afficher un message de débogage dans Fish, utilisez simplement `echo` ou `printf` avec votre message.

```Fish Shell
echo "Début du script"
# ... votre code...
echo "Valeur de la variable: $ma_variable"
# ... plus de votre code...
```

Sortie attendue:
```
Début du script
Valeur de la variable: truc
```

Utilisez `printf` pour plus de contrôle sur le format:

```Fish Shell
set ma_variable 42
printf "La réponse à la vie, l'univers et tout le reste est: %d\n" $ma_variable
```

Sortie attendue:
```
La réponse à la vie, l'univers et tout le reste est: 42
```

## Deep Dive
Dans l'histoire, l’affichage de sorties de débogage était souvent accompli avec des commandes simples comme `echo`. Avec le temps, les outils se sont sophistiqués, mais dans un shell, ces commandes basiques restent d'une grande aide. En Fish, l'utilisation de `echo` et `printf` est un choix naturel, mais il existe d'autres options plus avancées comme le débogage interactif avec `fish -d 3` pour augmenter le niveau de débogage.

## See Also
Pour plus d'astuces Fish ou pour approfondir vos connaissances en débogage, consultez:

- La documentation officielle de Fish: [https://fishshell.com/docs/current/index.html](https://fishshell.com/docs/current/index.html)
- Guide pour `printf` : [https://fishshell.com/docs/current/cmds/printf.html](https://fishshell.com/docs/current/cmds/printf.html)
- Info sur le débogage Fish: [https://fishshell.com/docs/current/index.html#debugging](https://fishshell.com/docs/current/index.html#debugging)