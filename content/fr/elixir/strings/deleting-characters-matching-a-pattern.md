---
aliases:
- /fr/elixir/deleting-characters-matching-a-pattern/
date: 2024-01-20 17:41:49.390394-07:00
description: "Supprimer des caract\xE8res selon un mod\xE8le (pattern) c'est enlever\
  \ des \xE9l\xE9ments d'une cha\xEEne qui correspondent \xE0 un crit\xE8re pr\xE9\
  cis. Les d\xE9veloppeurs le font\u2026"
lastmod: 2024-02-18 23:09:08.415999
model: gpt-4-1106-preview
summary: "Supprimer des caract\xE8res selon un mod\xE8le (pattern) c'est enlever des\
  \ \xE9l\xE9ments d'une cha\xEEne qui correspondent \xE0 un crit\xE8re pr\xE9cis.\
  \ Les d\xE9veloppeurs le font\u2026"
title: "Suppression de caract\xE8res correspondant \xE0 un motif"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Supprimer des caractères selon un modèle (pattern) c'est enlever des éléments d'une chaîne qui correspondent à un critère précis. Les développeurs le font pour nettoyer des données, valider des entrées ou manipuler du texte de manière contrôlée.

## How to: (Comment faire :)

Utilisons la fonction `String.replace/3` pour supprimer les caractères qui correspondent à un modèle défini par une expression régulière (regex).

```elixir
defmodule Cleaner do
  def delete_pattern(str, pattern) do
    String.replace(str, ~r/#{pattern}/, "")
  end
end

IO.puts Cleaner.delete_pattern("Bonjour1 les2 programmeurs3!", "\\d")
```

```  
Bonjour les programmeurs!
```

Dans cet exemple, le chiffre `\\d` est le modèle qui identifie tous les chiffres dans la chaîne de caractères, et ils sont supprimés.

## Deep Dive (Plongée en profondeur)

Historiquement, manipuler des chaînes de caractères a toujours été une partie cruciale de la programmation. En Elixir, c'est particulièrement vrai puisque le langage a été construit pour gérer des systèmes distribués et souvent, cela implique de traiter des données textuelles venant de diverses sources. 

Les alternatives à `String.replace/3` incluent l'utilisation de listes de compréhension ou de fonctions dans le module `Enum` pour filtrer caractère par caractère. Cependant, les expressions régulières offrent une solution concise et puissante pour des correspondances complexes.

En interne, Elixir utilise l'ingénierie de Erlang et les bibliothèques pour traiter les expressions régulières, optimisées pour l'efficacité et la vitesse.

## See Also (Voir également)

- Documentation Elixir sur `String.replace/3`: https://hexdocs.pm/elixir/String.html#replace/4
- Guide d'introduction aux expressions régulières en Elixir : https://elixir-lang.org/getting-started/pattern-matching.html
- Fiche récapitulative des expressions régulières (Regex Cheat Sheet) : https://www.debuggex.com/cheatsheet/regex/pcre
