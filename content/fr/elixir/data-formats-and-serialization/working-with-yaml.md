---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:04.778001-07:00
description: "YAML, acronyme de YAML Ain't Markup Language, est un standard de s\xE9\
  rialisation de donn\xE9es lisible par l'humain, couramment utilis\xE9 pour les fichiers\
  \ de\u2026"
lastmod: '2024-03-13T22:44:57.349523-06:00'
model: gpt-4-0125-preview
summary: "YAML, acronyme de YAML Ain't Markup Language, est un standard de s\xE9rialisation\
  \ de donn\xE9es lisible par l'humain, couramment utilis\xE9 pour les fichiers de\
  \ configuration et l'\xE9change de donn\xE9es entre langages avec diff\xE9rentes\
  \ structures de donn\xE9es."
title: Travailler avec YAML
weight: 41
---

## Comment faire :
Elixir n'inclut pas de support intégré pour YAML. Cependant, vous pouvez utiliser des bibliothèques tierces telles que `yamerl` ou `yaml_elixir` pour travailler avec YAML. Ici, nous nous concentrerons sur `yaml_elixir` pour sa facilité d'utilisation et ses fonctionnalités complètes.

Tout d'abord, ajoutez `yaml_elixir` à vos dépendances mix.exs :

```elixir
defp deps do
  [
    {:yaml_elixir, "~> 2.9"}
  ]
end
```

Ensuite, exécutez `mix deps.get` pour récupérer la nouvelle dépendance.

### Lire YAML
Étant donné un fichier YAML simple, `config.yaml`, qui ressemble à ceci :

```yaml
database:
  adapter: postgres
  username: user
  password: pass
```

Vous pouvez lire ce fichier YAML et le convertir en une map Elixir comme suit :

```elixir
defmodule Config do
  def read do
    {:ok, contenu} = YamlElixir.read_from_file("config.yaml")
    contenu
  end
end

# Exemple d'utilisation
Config.read()
# Sortie : 
# %{
#   "database" => %{
#     "adapter" => "postgres",
#     "username" => "user",
#     "password" => "pass"
#   }
# }
```

### Écrire en YAML
Pour écrire une map dans un fichier YAML :

```elixir
defmodule ConfigWriter do
  def write do
    contenu = %{
      database: %{
        adapter: "mysql",
        username: "root",
        password: "s3cret"
      }
    }
    
    YamlElixir.write_to_file("new_config.yaml", contenu)
  end
end

# Exemple d'utilisation
ConfigWriter.write()
# Cela créera ou écrasera `new_config.yaml` avec le contenu spécifié
```

Remarquez comment `yaml_elixir` permet une traduction directe entre les fichiers YAML et les structures de données Elixir, en faisant un excellent choix pour les programmeurs Elixir ayant besoin de travailler avec des données YAML.
