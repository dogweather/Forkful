---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 21:54:05.899915-07:00
description: "Gerar n\xFAmeros aleat\xF3rios no Visual Basic for Applications (VBA)\
  \ permite que programas simulem processos com elementos de chance ou variabilidade,\
  \ como a\u2026"
lastmod: '2024-03-13T22:44:46.407346-06:00'
model: gpt-4-0125-preview
summary: "Gerar n\xFAmeros aleat\xF3rios no Visual Basic for Applications (VBA) permite\
  \ que programas simulem processos com elementos de chance ou variabilidade, como\
  \ a rolagem de dados ou a amostragem de dados."
title: "Gerando n\xFAmeros aleat\xF3rios"
weight: 12
---

## Como Fazer:
No VBA, a função `Rnd` é usada para gerar números aleatórios. Por padrão, `Rnd` gera um número de ponto flutuante de precisão simples maior ou igual a 0 e menor que 1. Aqui estão alguns passos e exemplos para utilizar números aleatórios eficazmente:

1. **Número Aleatório Simples:**
   Para gerar um número aleatório básico, você só precisa chamar `Rnd()`:

   ```vb
   Sub GenerateRandomNumber()
       Dim randomNumber As Single
       randomNumber = Rnd() ' Número aleatório entre 0 e 1
       MsgBox randomNumber
   End Sub
   ```

2. **Definindo a Semente:**
   A instrução `Randomize` inicializa o gerador de números aleatórios, o que pode ser crucial para garantir resultados diferentes cada vez que seu código VBA é executado:

   ```vb
   Sub SeedRandomNumber()
       Randomize
       Dim randomNumber As Single
       randomNumber = Rnd()
       MsgBox randomNumber
   End Sub
   ```

3. **Gerando Números em um Intervalo:**
   Frequentemente, você desejará um número aleatório dentro de um intervalo específico. Veja como gerar um número entre 1 e 100:

   ```vb
   Sub RandomNumberInRange()
       Randomize
       Dim randomNumber As Integer
       randomNumber = Int((100 * Rnd()) + 1) ' Número aleatório entre 1 e 100
       MsgBox randomNumber
   End Sub
   ```

### Saída de Exemplo:
Após executar `RandomNumberInRange`, você pode ver uma caixa de mensagem exibindo um número como `45`.

## Aprofundando:
A função `Rnd` no VBA, embora fácil de usar, na verdade gera números pseudoaleatórios baseados em um algoritmo determinístico. Isso significa que as sequências de números que produz não são verdadeiramente aleatórias, mas muitas vezes podem ser suficientes para tarefas comuns que necessitam de processos estocásticos.

Historicamente, a capacidade de geração de números aleatórios no VBA remonta às primeiras versões do Basic, adaptando-se ao longo do tempo para incluir recursos como `Randomize` para melhorar a aleatoriedade, semeando o algoritmo com um ponto de partida. No entanto, para aplicações que exigem altos níveis de aleatoriedade, como operações criptográficas seguras, o `Rnd` do VBA pode não ser a melhor ferramenta. Alternativas em ambientes de programação mais robustos ou linguagens projetadas com a criptografia em mente, como o módulo `secrets` do Python ou o `SecureRandom` do Java, devem ser consideradas.

Apesar de suas limitações, a simplicidade e acessibilidade de gerar números aleatórios no VBA continuam a torná-lo uma ferramenta valiosa para uma ampla gama de aplicações mais leves, trabalhos de simulação e finalidades educacionais.
