---
title:                "Extraction de sous-chaînes"
aliases:
- /fr/fish-shell/extracting-substrings/
date:                  2024-01-20T17:45:31.333103-07:00
model:                 gpt-4-1106-preview
simple_title:         "Extraction de sous-chaînes"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/fish-shell/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why?
Extraire des sous-chaînes, c'est comme découper un morceau précis de votre baguette préférée. Les programmeurs le font pour manipuler, analyser ou simplement afficher un fragment spécifique d'un texte.

## How to:
Dans Fish, extrayons des morceaux de chaînes de caractères. Imaginez que vous avez un morceau de texte et que vous voulez juste un bout.

```Fish Shell
set phrase "Bonjour, je suis un script Fish!"
echo $phrase[9..12]  # Extraire "je"
echo $phrase[9..-1]  # Extraire "je suis un script Fish!"
```

Sortie:
```
je
je suis un script Fish!
```

Vous pouvez aussi définir le début et la fin.

```Fish Shell
set phrase "Pain au chocolat ou chocolatine?"
echo $phrase[1..4]    # Extraire "Pain"
echo $phrase[-12..-1] # Extraire "chocolatine?"
```

Sortie:
```
Pain
chocolatine?
```

## Deep Dive
Historiquement, l'extraction de sous-chaînes est une fonctionnalité présente dans de nombreux langages, car les chaînes de caractères sont fondamentales en programmation. Dans le shell classique, `cut`, `awk`, `grep` peuvent faire le travail, mais sont moins intuitifs.

Fish offre une syntaxe claire, inspirée des langages comme Python. Il utilise des index basés sur 1, ce qui est naturel pour beaucoup d'utilisateurs (pas de tête cassée avec les index à partir de 0). Les index négatifs pour compter depuis la fin, c'est comme vérifier combien il reste de tranches dans la baguette sans la sortir du sac.

Fish rend aussi superflu l'usage de commandes externes pour des tâches simples, ce qui signifie moins de pipes et de subshells, donc des scripts plus lisibles et performants. C'est pur Fish et ça garde script frais et croustillant.

## See Also
Pour creuser, voici des liens :

- Documentation officielle de Fish sur les chaînes de caractères : [https://fishshell.com/docs/current/index.html#expand-index-range](https://fishshell.com/docs/current/index.html#expand-index-range)
- Tutoriel Fish sur les manipulations de chaînes : [https://fishshell.com/docs/current/tutorial.html#tut_strings](https://fishshell.com/docs/current/tutorial.html#tut_strings)
