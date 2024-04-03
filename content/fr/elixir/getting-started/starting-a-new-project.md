---
date: 2024-01-20 18:03:15.779659-07:00
description: "Le d\xE9marrage d'un nouveau projet, c'est un peu aller \xE0 l'aventure\
  \ avec Elixir : on commence avec une id\xE9e et des outils pour cr\xE9er quelque\
  \ chose d'utile\u2026"
lastmod: '2024-03-13T22:44:57.327735-06:00'
model: gpt-4-1106-preview
summary: "Le d\xE9marrage d'un nouveau projet, c'est un peu aller \xE0 l'aventure\
  \ avec Elixir : on commence avec une id\xE9e et des outils pour cr\xE9er quelque\
  \ chose d'utile ou fun."
title: Lancement d'un nouveau projet
weight: 1
---

## Comment faire :
Pour débuter, on a besoin de `mix`, l'outil de build d'Elixir. On crée un projet en tapant :

```elixir
mix new mon_projet
```

On obtient :

```
* creating README.md
* creating .formatter.exs
* creating .gitignore
* creating mix.exs
* creating lib
* creating lib/mon_projet.ex
* creating test
* creating test/test_helper.exs
* creating test/mon_projet_test.exs

Your Mix project was created successfully.
You can use "mix" to compile it, test it, and more:

    cd mon_projet
    mix test

Run "mix help" for more commands.
```

Félicitations ! Vous avez votre structure de base.

## Plongée profonde
Historiquement, Elixir est né de la nécessité de combiner la programmabilité expressive de Ruby avec la concurrentialité et la fiabilité du langage Erlang. `mix` est son principal outil de création, de compilation et de gestion de projets, inspiré par le succès de `bundle` et `rake` en Ruby, mais adapté à l'écosystème de la machine virtuelle BEAM (Erlang).

Il y a des alternatives comme rebar3 pour Erlang, mais mix est conçu spécifiquement pour les projets Elixir. Quand vous utilisez `mix new`, il crée une structure de dossiers et fichiers pertinents : des métadonnées de projet dans `mix.exs`, le code source dans `lib` et des tests dans `test`. C'est une convention qui aide à rester organisé dès le début.

Détail amusant, les tests sont une partie cruciale en Elixir grâce à l'adoption de la philosophie du développement piloté par les tests (Test-Driven Development - TDD). Dès la création, `mix` vous incite à penser aux tests avec `test/mon_projet_test.exs`.

## Voir aussi
- Documentation officielle Elixir, "Mix", [https://elixir-lang.org/getting-started/mix-otp/introduction-to-mix.html](https://elixir-lang.org/getting-started/mix-otp/introduction-to-mix.html)
- Elixir School, pour une approche plus didactique, [https://elixirschool.com/fr/](https://elixirschool.com/fr/)
- La communauté Elixir sur elixirforum.com, [https://elixirforum.com/](https://elixirforum.com/)
- Un exemple de projet Elixir sur GitHub, pour s'inspirer, [https://github.com/elixir-lang/elixir](https://github.com/elixir-lang/elixir)
