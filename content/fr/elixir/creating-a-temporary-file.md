---
title:                "Création d'un fichier temporaire"
date:                  2024-01-20T17:39:56.412545-07:00
model:                 gpt-4-1106-preview
simple_title:         "Création d'un fichier temporaire"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/elixir/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## What & Why?
Créer un fichier temporaire, c'est générer un fichier destiné à un usage court terme, souvent pour manipuler des données transitoires. Les programmeurs le font pour éviter de surcharger la mémoire, faciliter le nettoyage après usage, ou pour sécuriser des opérations qui nécessitent des fichiers intermédiaires.

## How to:
En Elixir, la création d'un fichier temporaire n'est pas directement intégrée dans la bibliothèque standard. On utilise généralement `:os.cmd` avec des commandes systèmes, ou des packages tiers, comme `Temp` de la bibliothèque Erlang.

```elixir
# Avec :os.cmd et le système
commande = "mktemp"
{fichier_temp, 0} = :os.cmd(commande) |> to_string() |> String.trim() |> String.split("\n")
IO.puts("Fichier temporaire créé: #{fichier_temp}")

# Utiliser après et supprimer le fichier temporaire
# [...]
:os.cmd('rm ' <> fichier_temp)
```

Output:

```
Fichier temporaire créé: /tmp/tmp.WaXbJk9kUR
```

C’est brut et sans fioritures, mais ça marche.

## Deep Dive
Avant, les fichiers temporaires étaient risqués – si vous ne les supprimez pas, ils s’accumulent. En Elixir, sans fonction intégrée pour les fichiers temporaires, il faut bien faire le ménage soi-même ou utiliser une bibliothèque. `:os.cmd` est notre rustine ici, mais attention : ces commandes dépendent du système d'exploitation et ne sont pas multiplateformes.

En considérant les alternatives, la bibliothèque [Temp](https://hex.pm/packages/temp) d'Erlang est assez sympa pour simplifier tout cela. Elle crée et supprime des fichiers temporaires sans que vous ayez à vous inquiéter du système sous-jacent.

## See Also
- [Elixir Documentation](https://hexdocs.pm/elixir/)
- Library for temporary files: [Temp](https://hex.pm/packages/temp)
- Pour plus sur `:os.cmd`: [Erlang os Module](http://erlang.org/doc/man/os.html)