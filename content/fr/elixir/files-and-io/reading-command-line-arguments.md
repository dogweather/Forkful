---
date: 2024-01-20 17:56:09.361779-07:00
description: "Lire des arguments de la ligne de commande, c'est r\xE9cup\xE9rer les\
  \ donn\xE9es qu'un utilisateur entre lorsqu'il ex\xE9cute votre programme. Les programmeurs\
  \ font\u2026"
lastmod: '2024-03-13T22:44:57.343911-06:00'
model: gpt-4-1106-preview
summary: "Lire des arguments de la ligne de commande, c'est r\xE9cup\xE9rer les donn\xE9\
  es qu'un utilisateur entre lorsqu'il ex\xE9cute votre programme."
title: Lecture des arguments de ligne de commande
weight: 23
---

## Comment faire :
```elixir
# Pour récupérer tous les arguments :
args = System.argv()
IO.inspect(args)

# Pour exécuter :
# elixir script.exs arg1 arg2 arg3

# Sortie attendue :
# ["arg1", "arg2", "arg3"]
```

```elixir
# Pour utiliser un argument spécifique, comme si on voulait le premier :
[first_arg | _] = System.argv()
IO.puts "Le premier argument est : #{first_arg}"

# Sortie si on exécute `elixir script.exs salut` :
# Le premier argument est : salut
```

## Exploration :
Historiquement, la lecture des arguments de la ligne de commande vient des premiers jours de l'informatique, car c'était le moyen principal d'interagir avec les logiciels. Dans Elixir, `System.argv()` est la façon la plus simple de les récupérer, mais on peut aussi utiliser des bibliothèques comme `OptionParser` pour plus de fonctionnalités, comme valider et caster les valeurs, ou même pour créer de l'aide automatiquement.

Par ailleurs, Elixir étant basé sur Erlang, il hérite également de ses méthodes de lecture des arguments de la ligne de commande. Quand on lance un script Elixir, on peut également passer des arguments à la machine virtuelle Erlang (par exemple, pour contrôler le comportement du garbage collector).

Enfin, côté implémentation, `System.argv()` est un appel de fonction qui interroge les données déjà parsées et stockées par la machine virtuelle au moment du démarrage du programme. Cela signifie que le coût en performance est minime et que l'utilisation est très simple.

## Voir également :
- [Documentation officielle de Elixir sur System.argv()](https://hexdocs.pm/elixir/System.html#argv/0)
- [Guide d'introduction à OptionParser d'Elixir](https://hexdocs.pm/elixir/OptionParser.html)
- [Discussions et exemples sur le forum Elixir](https://elixirforum.com)
