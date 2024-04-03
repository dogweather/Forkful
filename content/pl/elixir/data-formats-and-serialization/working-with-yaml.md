---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:22.421406-07:00
description: "YAML, co oznacza \"YAML Ain't Markup Language\" (YAML nie jest j\u0119\
  zykiem znacznik\xF3w), to standard serializacji danych czytelny dla cz\u0142owieka,\
  \ kt\xF3ry jest\u2026"
lastmod: '2024-03-13T22:44:35.065153-06:00'
model: gpt-4-0125-preview
summary: "YAML, co oznacza \"YAML Ain't Markup Language\" (YAML nie jest j\u0119zykiem\
  \ znacznik\xF3w), to standard serializacji danych czytelny dla cz\u0142owieka, kt\xF3\
  ry jest powszechnie stosowany w plikach konfiguracyjnych oraz w wymianie danych\
  \ mi\u0119dzy j\u0119zykami o r\xF3\u017Cnych strukturach danych."
title: Praca z YAML
weight: 41
---

## Jak to zrobić:
Elixir nie zawiera wbudowanego wsparcia dla YAML. Można jednak korzystać z bibliotek firm trzecich, takich jak `yamerl` lub `yaml_elixir`, aby pracować z YAML. Tutaj skupimy się na `yaml_elixir` ze względu na jego łatwość użycia i obszerne funkcje.

Po pierwsze, dodaj `yaml_elixir` do zależności w pliku mix.exs:

```elixir
defp deps do
  [
    {:yaml_elixir, "~> 2.9"}
  ]
end
```

Następnie uruchom `mix deps.get`, aby pobrać nową zależność.

### Czytanie YAML
Biorąc pod uwagę prosty plik YAML, `config.yaml`, który wygląda tak:

```yaml
database:
  adapter: postgres
  username: user
  password: pass
```

Możesz odczytać ten plik YAML i przekonwertować go na mapę Elixir tak:

```elixir
defmodule Config do
  def read do
    {:ok, content} = YamlElixir.read_from_file("config.yaml")
    content
  end
end

# Przykładowe użycie
Config.read()
# Wynik: 
# %{
#   "database" => %{
#     "adapter" => "postgres",
#     "username" => "user",
#     "password" => "pass"
#   }
# }
```

### Pisanie YAML
Aby zapisać mapę z powrotem do pliku YAML:

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

# Przykładowe użycie
ConfigWriter.write()
# To utworzy lub nadpisze `new_config.yaml` z podaną zawartością
```

Zauważ, jak `yaml_elixir` umożliwia proste tłumaczenie między plikami YAML a strukturami danych Elixir, co czyni go doskonałym wyborem dla programistów Elixir potrzebujących pracować z danymi YAML.
