---
date: 2024-01-27 20:34:53.990766-07:00
description: "Gerar n\xFAmeros aleat\xF3rios envolve criar n\xFAmeros que n\xE3o podem\
  \ ser previstos de maneira razo\xE1vel melhor do que por acaso, o que \xE9 essencial\
  \ para o\u2026"
lastmod: '2024-03-13T22:44:46.149606-06:00'
model: gpt-4-0125-preview
summary: "Gerar n\xFAmeros aleat\xF3rios envolve criar n\xFAmeros que n\xE3o podem\
  \ ser previstos de maneira razo\xE1vel melhor do que por acaso, o que \xE9 essencial\
  \ para o desenvolvimento de simula\xE7\xF5es, jogos e algoritmos de seguran\xE7\
  a."
title: "Gera\xE7\xE3o de n\xFAmeros aleat\xF3rios"
weight: 12
---

## Como fazer:
Python oferece o módulo `random` que ajuda na geração de números aleatórios para vários usos. Veja como começar:

1. **Importando o módulo**
    ```Python
    import random
    ```

2. **Gerando um Inteiro Aleatório**
    Entre quaisquer dois números.
    ```Python
    random_integer = random.randint(1, 10)
    print(random_integer)
    ```
    Saída de amostra: `7`

3. **Gerando um Float**
    Entre 0 e 1.
    ```Python
    random_float = random.random()
    print(random_float)
    ```
    Saída de amostra: `0.436432634653`

    Se precisar de um float em uma faixa diferente, multiplique:
    ```Python
    random_float_range = random.random() * 5  # 0 a 5
    print(random_float_range)
    ```
    Saída de amostra: `3.182093745`

4. **Selecionando um Elemento Aleatório de uma Lista**
    ```Python
    greetings = ['Olá', 'Oi', 'Hey', 'Hola', 'Bonjour']
    print(random.choice(greetings))
    ```
    Saída de amostra: `Hola`

5. **Embaralhando uma Lista**
    Perfeito para jogos de cartas ou qualquer aplicação que precise randomizar a ordem.
    ```Python
    numbers = list(range(10))
    random.shuffle(numbers)
    print(numbers)
    ```
    Saída de amostra: `[2, 5, 0, 4, 9, 8, 1, 7, 6, 3]`

## Aprofundamento
O módulo `random` no Python utiliza um gerador de números pseudoaleatórios (PRNG), especificamente o algoritmo Mersenne Twister, que é bom para aplicações de uso geral, mas não é adequado para fins criptográficos devido à sua previsibilidade se muitas saídas forem observadas. O módulo `secrets`, introduzido no Python 3.6, oferece uma alternativa melhor para a geração de números aleatórios criptograficamente fortes, especialmente útil em aplicações sensíveis à segurança. Por exemplo, gerar um token aleatório seguro para um link de redefinição de senha:

```Python
import secrets
token = secrets.token_hex(16)
print(token)
```

Historicamente, gerar números aleatórios que são verdadeiramente aleatórios tem sido um desafio na computação, com os métodos iniciais dependendo de fenômenos físicos ou sementes inseridas manualmente. O desenvolvimento e a adoção de algoritmos como o Mersenne Twister (usado por padrão no módulo `random` do Python até pelo menos minha última atualização de conhecimento em 2023) marcaram um progresso significativo. No entanto, a busca contínua por algoritmos mais seguros e eficientes levou à inclusão do módulo `secrets` para tarefas relacionadas à criptografia. Essa evolução reflete a crescente importância da segurança no desenvolvimento de software e a necessidade de uma aleatoriedade mais robusta em aplicações que vão desde a criptografia até a geração de tokens seguros.
