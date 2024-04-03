---
date: 2024-01-20 17:52:15.302983-07:00
description: "Imprimer des messages de d\xE9bogage, c'est \xE9crire des infos temporaires\
  \ dans votre console pour comprendre comment votre code Elixir se comporte en direct.\u2026"
lastmod: '2024-03-13T22:44:57.329944-06:00'
model: gpt-4-1106-preview
summary: "Imprimer des messages de d\xE9bogage, c'est \xE9crire des infos temporaires\
  \ dans votre console pour comprendre comment votre code Elixir se comporte en direct."
title: "Affichage des sorties de d\xE9bogage"
weight: 33
---

## Comment faire :
```elixir
defmodule Debutant do
  def exemple do
    IO.puts "Voici un message de debug simple"
    
    valeur = 42
    IO.inspect valeur, label: "La valeur inspectée"

    liste = [1, 2, 3, 4]
    IO.inspect liste, label: "Contenu de la liste"
  end
end

Debutant.exemple
```
Sortie :
```
Voici un message de debug simple
La valeur inspectée: 42
Contenu de la liste: [1, 2, 3, 4]
```

## Exploration en profondeur
Historiquement, `IO.puts` et `IO.inspect` sont les moyens de base pour imprimer le debug en Elixir, un langage qui tire ses racines d'Erlang - célèbre pour sa robustesse. `IO.inspect` est pratique avec son label optionnel pour clarifier le contexte directement dans le flux de sortie. Autre choix : Logger, plus riche mais plus lourd, conçu pour suivre des événements au sein des systèmes de production. Sous le capot, `IO.inspect` s'appuie sur le protocole `Inspect`, ce qui permet d'avoir une représentation lisible de n'importe quelle structure de données Elixir personnalisée.

## Voir aussi
- [Documentation officielle de `IO`](https://hexdocs.pm/elixir/IO.html)
- [Guide de démarrage d'Elixir `IO.inspect`](https://elixir-lang.org/getting-started/debugging.html#i-o-inspect)
- [Documentation sur le protocole `Inspect`](https://hexdocs.pm/elixir/Inspect.Opts.html)
- [Guide sur `Logger`](https://hexdocs.pm/logger/Logger.html)
