---
aliases:
- /fr/elixir/searching-and-replacing-text/
date: 2024-01-20 17:57:26.684591-07:00
description: "Chercher et remplacer du texte, c'est update un morceau de texte par\
  \ un autre. Les devs font \xE7a pour corriger des erreurs, mettre \xE0 jour des\
  \ donn\xE9es ou\u2026"
lastmod: 2024-02-18 23:09:08.417285
model: gpt-4-1106-preview
summary: "Chercher et remplacer du texte, c'est update un morceau de texte par un\
  \ autre. Les devs font \xE7a pour corriger des erreurs, mettre \xE0 jour des donn\xE9\
  es ou\u2026"
title: Recherche et remplacement de texte
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Chercher et remplacer du texte, c'est update un morceau de texte par un autre. Les devs font ça pour corriger des erreurs, mettre à jour des données ou automatiser des modifications.

## How to (Comment faire ?)
Elixir utilise les Regex (expressions régulières) pour la recherche, avec `String.replace/3` pour le remplacement.

```elixir
# Chercher et remplacer 'monde' par 'Elixir'
original_text = "Bonjour monde"
new_text = String.replace(original_text, "monde", "Elixir")
IO.puts(new_text)
```

Resultat :
```
Bonjour Elixir
```

Si on veut remplacer toutes les instances d'un pattern :

```elixir
# Remplacer toutes les voyelles par un astérisque
text_with_voyelles = "Remplacer les voyelles est amusant."
text_with_asterisks = String.replace(text_with_voyelles, ~r/[aeiouy]/, "*")
IO.puts(text_with_asterisks)
```

Resultat :
```
R*mpl*c*r l*s v*y*ll*s *st *m*s*nt.
```

## Deep Dive (Plongée en profondeur)
Historiquement, la recherche et le remplacement de texte dérivent des premières manipulations de chaînes de caractères en informatique, élémentaires pour l'édition de texte. 

Dans Elixir, le module `String` gère les opérations sur les chaînes unicode et utilise des Regex pour des recherches plus complexes. Ces opérations sont basées sur la librairie Erlang `:re`, qui est un wrapper autour de la librairie PCRE (Perl Compatible Regular Expressions).

Il existe des alternatives au module `String` pour des cas d'usage spécifiques. Par exemple, `Regex.run/3` vous donne les captures d'une regex, et `Regex.scan/3` trouve toutes les occurrences d'un pattern.

L'implémentation derrière `String.replace/3` permet non seulement de remplacer par un texte statique mais aussi en utilisant des fonctions. Ainsi, on peut transformer le texte capturé avant le remplacement.

## See Also (Voir Aussi)
- [Documentation Elixir pour `String.replace/3`](https://hexdocs.pm/elixir/String.html#replace/3)
- [Documentation Elixir pour le module `Regex`](https://hexdocs.pm/elixir/Regex.html)
- [PCRE documentation](http://www.pcre.org/)
