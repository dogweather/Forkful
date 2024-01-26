---
title:                "Trouver la longueur d'une chaîne de caractères"
date:                  2024-01-20T17:47:19.971983-07:00
model:                 gpt-4-1106-preview
simple_title:         "Trouver la longueur d'une chaîne de caractères"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/elixir/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Trouver la longueur d'une chaîne de caractères, c'est déterminer le nombre de caractères qu'elle contient. Les programmeurs font ça pour valider des entrées, formater du texte, ou simplement pour interagir avec les données de manière contrôlée.

## How to:
En Elixir, la longueur d'une chaîne est trouvée avec la fonction `String.length/1`. Voici comment ça marche :

```elixir
string = "Bonjour le monde"
longueur = String.length(string)
IO.puts(longueur)  # Affiche 16
```

Si on utilise des caractères Unicode, ça reste aussi simple :

```elixir
str_unicode = "😀😃😄"
IO.puts(String.length(str_unicode))  # Affiche 3
```

La longueur retourne le nombre de graphèmes, pas nécessairement le nombre d'octets ou de points de code Unicode.

## Deep Dive
Avant Elixir, d'autres langages avaient leurs manières de faire — par exemple, en Python, c'est `len("chaîne")`. Ce qui rend Elixir spécial, c'est qu'il compte les graphèmes. En UTF-8, un caractère comme "é" peut être représenté par plusieurs octets. Elixir gère ça tranquillement.

Alternatives? On pourrait compter les octets (`byte_size/1`) ou les points de code (`String.codepoints/1` et les compter), mais ce n'est pas idéal pour la longueur "visuelle" de la chaîne.

Implementation details? `String.length/1` utilise le module `String.Unicode` d'Elixir pour parcourir correctement les graphèmes. C'est robuste, supportant même les caractères combinants.

## See Also
- [Elixir documentation for String module](https://hexdocs.pm/elixir/String.html)
- [Unicode Standard](http://www.unicode.org/standard/standard.html)
