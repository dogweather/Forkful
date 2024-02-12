---
title:                "Concatenando strings"
aliases:
- /pt/vba/concatenating-strings/
date:                  2024-02-01T21:50:30.513813-07:00
model:                 gpt-4-0125-preview
simple_title:         "Concatenando strings"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/vba/concatenating-strings.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Por Quê?

A concatenação no Visual Basic for Applications (VBA) envolve a união de duas ou mais strings em uma única entidade. Esta é uma tarefa fundamental na programação, essencial para gerar mensagens para o usuário, criar consultas SQL e mais, pois permite a criação e manipulação dinâmica de dados de string.

## Como fazer:

O VBA oferece um método direto para concatenar strings usando o operador `&` ou a função `Concatenate`. Vamos explorar ambos os métodos com exemplos:

1. **Usando o Operador `&`:**

O operador `&` é o método mais comum para concatenar strings no VBA. É simples e eficiente para unir múltiplas strings.

```vb.net
Dim firstName As String
Dim lastName As String
firstName = "Jane"
lastName = "Doe"
' Concatenando strings
Dim fullName As String
fullName = firstName & " " & lastName
Debug.Print fullName 'Saída: Jane Doe
```

2. **Usando a Função `Concatenate`:**

Alternativamente, o VBA permite a concatenação de strings usando a função `Concatenate`, o que é especialmente útil ao lidar com um array de strings ou quando você prefere uma sintaxe de função.

```vb.net
Dim greetings As String
Dim name As String
greetings = "Olá"
name = "John"
' Concatenando strings usando a função Concatenate
Dim message As String
message = Application.WorksheetFunction.Concatenate(greetings, " ", name, "!")
Debug.Print message 'Saída: Olá John!
```

A escolha entre o operador `&` e a função `Concatenate` depende da preferência pessoal e dos requisitos específicos do seu projeto.

## Aprofundamento

A concatenação de strings é um recurso básico, mas poderoso no VBA, com suas raízes remontando às linguagens de programação antigas. A prevalência do operador `&` no VBA para concatenação, em detrimento do operador `+`, comumente usado em muitas outras linguagens, sublinha o foco do VBA no tratamento explícito de strings, evitando assim incompatibilidades e erros involuntários de tipo de dados.

Embora o operador `&` seja eficiente e amplamente adotado, a função `Concatenate` se destaca em cenários que requerem mais clareza ou lidam com casos especiais de concatenação, como ao tratar arrays. No entanto, é importante notar que versões modernas do Excel introduziram a função `TEXTJOIN`, que pode ser mais eficiente para concatenar arrays de strings com um delimitador, embora não seja diretamente parte do VBA.

Ao lidar com manipulações extensivas de strings ou aplicações críticas para o desempenho, os programadores podem explorar alternativas como usar a classe `StringBuilder` no .NET (acessível via COM no VBA). Isso pode aumentar significativamente o desempenho, particularmente em laços ou ao concatenar um grande número de strings, devido aos seus padrões de uso de memória mais eficientes.

Em última análise, escolher o método correto para concatenar strings no VBA depende das suas necessidades específicas, considerações de desempenho e legibilidade. Seja optando pela simplicidade do operador `&` ou pela funcionalidade da função `Concatenate`, entender as implicações e a eficiência de cada abordagem é crucial para a manipulação eficaz de strings no VBA.
