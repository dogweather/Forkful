---
title:                "Lendo argumentos da linha de comando"
aliases:
- pt/python/reading-command-line-arguments.md
date:                  2024-01-20T17:57:06.213806-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lendo argumentos da linha de comando"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/python/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## O Que & Porquê?
Ler argumentos de linha de comando significa pegar dados que o usuário passa diretamente ao seu script Python quando o executa. Fazemos isso para tornar nossos programas mais dinâmicos e interativos, permitindo diferentes comportamentos com base no que o usuário especifica.

## Como Fazer:
Para ler argumentos de linha de comando em Python, usamos o módulo `sys`. Veja como é fácil:

```Python
import sys

# 'sys.argv' é uma lista com os argumentos.
# O primeiro elemento é sempre o nome do script.

print("Nome do script:", sys.argv[0])

# Argumentos passados pelo usuário
argumentos = sys.argv[1:]  # do segundo elemento em diante
print("Argumentos:", argumentos)

if argumentos:
    print(f"Primeiro argumento: {argumentos[0]}")
```

Se salvarmos esse script como `argumentos.py` e o rodarmos com `python argumentos.py banana maçã`, o resultado será:

```
Nome do script: argumentos.py
Argumentos: ['banana', 'maçã']
Primeiro argumento: banana
```

## Mergulho Profundo
Historicamente, acessar argumentos de linha de comando é uma prática antiga, vista em muitas linguagens de programação, porque é uma forma direta de interagir com scripts e programas. Além do módulo `sys`, você pode usar o módulo `argparse` para criar interfaces de linha de comando mais complexas e amigáveis. `argparse` permite definir tipos de dados para seus argumentos, fornecer mensagens de ajuda, e lidar com argumentos opcionais ou obrigatórios de uma maneira mais estruturada.

Implementando com `argparse`:

```Python
import argparse

# Cria o parser
parser = argparse.ArgumentParser(description='Exemplo com argparse.')

# Adiciona os argumentos que o programa aceitará
parser.add_argument('frutas', nargs='+', help='Uma lista de frutas.')

# Faz o parsing dos argumentos
args = parser.parse_args()

# Usa os argumentos
print(f"Frutas recebidas: {', '.join(args.frutas)}")
```

Se executarmos `python script.py banana maçã`, vamos obter:

```
Frutas recebidas: banana, maçã
```

## Veja Também
- Documentação oficial do módulo `sys`: https://docs.python.org/3/library/sys.html
- Documentação oficial do módulo `argparse`: https://docs.python.org/3/library/argparse.html
- Tutorial de `argparse` para aprofundamento: https://docs.python.org/3/howto/argparse.html
- Um guia prático para a linha de comando do Linux que complementa o uso de argumentos: https://linuxcommand.org/
