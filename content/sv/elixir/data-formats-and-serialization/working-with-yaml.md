---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:22.332085-07:00
description: "YAML, som st\xE5r f\xF6r YAML Ain't Markup Language, \xE4r en standard\
  \ f\xF6r serialisering av data som \xE4r l\xE4sbar f\xF6r m\xE4nniskor och som vanligtvis\
  \ anv\xE4nds f\xF6r\u2026"
lastmod: '2024-03-13T22:44:37.587897-06:00'
model: gpt-4-0125-preview
summary: "YAML, som st\xE5r f\xF6r YAML Ain't Markup Language, \xE4r en standard f\xF6\
  r serialisering av data som \xE4r l\xE4sbar f\xF6r m\xE4nniskor och som vanligtvis\
  \ anv\xE4nds f\xF6r konfigurationsfiler och datadelning mellan spr\xE5k med olika\
  \ datastrukturer."
title: Att Arbeta med YAML
weight: 41
---

## Hur man gör:
Elixir inkluderar inte inbyggt stöd för YAML. Du kan dock använda tredjepartsbibliotek såsom `yamerl` eller `yaml_elixir` för att arbeta med YAML. Här kommer vi att fokusera på `yaml_elixir` på grund av dess användarvänlighet och omfattande funktioner.

Först, lägg till `yaml_elixir` i dina beroenden i mix.exs:

```elixir
defp deps do
  [
    {:yaml_elixir, "~> 2.9"}
  ]
end
```

Kör sedan `mix deps.get` för att hämta det nya beroendet.

### Läsa YAML
Givet en enkel YAML-fil, `config.yaml`, som ser ut så här:

```yaml
database:
  adapter: postgres
  username: user
  password: pass
```

Du kan läsa denna YAML-fil och konvertera den till en Elixir-mapp på följande sätt:

```elixir
%module Config do
  def read do
    {:ok, content} = YamlElixir.read_from_file("config.yaml")
    content
  end
end

# Exempelanvändning
Config.read()
# Output: 
# %{
#   "database" => %{
#     "adapter" => "postgres",
#     "username" => "user",
#     "password" => "pass"
#   }
# }
```

### Skriva YAML
För att skriva en mapp tillbaka till en YAML-fil:

```elixir
defmodule ConfigWriter do
  def write do
    content = %{
      database: %{
        adapter: "mysql",
        username: "root",
        password: "s3cret"
      }
    }
    
    YamlElixir.write_to_file("new_config.yaml", content)
  end
end

# Exempelanvändning
ConfigWriter.write()
# Detta kommer att skapa eller skriva över `new_config.yaml` med det angivna innehållet
```

Notera hur `yaml_elixir` möjliggör en enkel översättning mellan YAML-filer och Elixir-datastrukturer, vilket gör det till ett utmärkt val för Elixir-programmerare som behöver arbeta med YAML-data.
