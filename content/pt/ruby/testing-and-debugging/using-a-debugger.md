---
aliases:
- /pt/ruby/using-a-debugger/
date: 2024-01-26 04:09:50.906949-07:00
description: "Usar um depurador (debugger) em Ruby d\xE1 aos programadores o superpoder\
  \ de pausar o c\xF3digo, inspecionar vari\xE1veis e avan\xE7ar atrav\xE9s do c\xF3\
  digo linha por\u2026"
lastmod: 2024-02-18 23:08:58.670174
model: gpt-4-0125-preview
summary: "Usar um depurador (debugger) em Ruby d\xE1 aos programadores o superpoder\
  \ de pausar o c\xF3digo, inspecionar vari\xE1veis e avan\xE7ar atrav\xE9s do c\xF3\
  digo linha por\u2026"
title: Usando um depurador
---

{{< edit_this_page >}}

## O Quê e Por Quê?

Usar um depurador (debugger) em Ruby dá aos programadores o superpoder de pausar o código, inspecionar variáveis e avançar através do código linha por linha. As pessoas fazem isso para eliminar bugs, entender o fluxo do código e ver exatamente o que seus feitiços escritos (código) estão fazendo quando a magia acontece — ou não.

## Como fazer:

O Ruby vem com um depurador embutido chamado `byebug`. Primeiro, inclua `byebug` no seu Gemfile e execute `bundle install`. Depois, coloque `byebug` exatamente onde você quer que seu programa faça uma pausa.

```Ruby
require 'byebug'

def calculate_magic(number)
  byebug
  magic_number = number * 7
  return magic_number
end

puts calculate_magic(6)
```

Executar este script irá interromper a execução em `byebug`, e você será levado para uma sessão interativa, onde você pode digitar comandos como:

```
step
next
continue
var local
```

A saída de exemplo lhe dará um prompt assim:

```
[2, 11] in example.rb
    2:
    3: def calculate_magic(number)
    4:   byebug
=>  5:   magic_number = number * 7
    6:   return magic_number
    7: end
    8:
    9: puts calculate_magic(6)
(byebug)
```

## Aprofundamento:

Muito antes do `byebug`, os Rubyistas usavam `debugger` e `pry`. Este último, `pry`, é mais do que um depurador; é um REPL poderoso que também pode ser usado para depuração com o ponto de interrupção `binding.pry`.

Alternativas ao `byebug` do Ruby incluem `pry-byebug`, que combina a funcionalidade de `pry` com `byebug`, e `ruby-debug`, que é uma gem mais antiga não mantida ativamente.

Quando você invoca o `byebug`, o depurador suspende a execução do seu código e lhe dá uma visão da execução. Você pode ver e alterar variáveis, saltar para diferentes pontos no código e até executar algumas linhas de código Ruby linha por linha. É meio que ter habilidades de viagem no tempo para o seu código Ruby.

## Veja Também:

- Repositório no GitHub do Byebug: [https://github.com/deivid-rodriguez/byebug](https://github.com/deivid-rodriguez/byebug)
- Documentação do Pry: [https://github.com/pry/pry](https://github.com/pry/pry)
- Um Guia para Depurar Aplicações Rails: [https://guides.rubyonrails.org/debugging_rails_applications.html](https://guides.rubyonrails.org/debugging_rails_applications.html)
