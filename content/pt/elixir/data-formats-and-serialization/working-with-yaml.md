---
title:                "Trabalhando com YAML"
aliases:
- /pt/elixir/working-with-yaml/
date:                  2024-02-03T19:25:08.055660-07:00
model:                 gpt-4-0125-preview
simple_title:         "Trabalhando com YAML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/elixir/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O quê e Por quê?

YAML, abreviação de YAML Ain't Markup Language, é um padrão de serialização de dados legível por humanos comumente usado para arquivos de configuração e troca de dados entre linguagens com diferentes estruturas de dados. Programadores o utilizam devido à sua simplicidade e capacidade de representar facilmente dados hierárquicos complexos.

## Como fazer:

Elixir não inclui suporte embutido para YAML. No entanto, você pode usar bibliotecas de terceiros, como `yamerl` ou `yaml_elixir`, para trabalhar com YAML. Aqui, vamos nos concentrar em `yaml_elixir` pela sua facilidade de uso e recursos abrangentes.

Primeiro, adicione `yaml_elixir` às suas dependências em mix.exs:

```elixir
defp deps do
  [
    {:yaml_elixir, "~> 2.9"}
  ]
end
```

Depois, execute `mix deps.get` para buscar a nova dependência.

### Lendo YAML

Dado um simples arquivo YAML, `config.yaml`, que se parece com isto:

```yaml
database:
  adapter: postgres
  username: user
  password: pass
```

Você pode ler este arquivo YAML e convertê-lo para um mapa Elixir assim:

```elixir
defmodule Config do
  def read do
    {:ok, content} = YamlElixir.read_from_file("config.yaml")
    content
  end
end

# Exemplo de uso
Config.read()
# Saída: 
# %{
#   "database" => %{
#     "adapter" => "postgres",
#     "username" => "user",
#     "password" => "pass"
#   }
# }
```

### Escrevendo YAML

Para escrever um mapa de volta para um arquivo YAML:

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

# Exemplo de uso
ConfigWriter.write()
# Isso criará ou sobrescreverá `new_config.yaml` com o conteúdo especificado
```

Note como `yaml_elixir` permite uma tradução direta entre arquivos YAML e estruturas de dados Elixir, tornando-o uma excelente escolha para programadores Elixir que precisam trabalhar com dados YAML.
