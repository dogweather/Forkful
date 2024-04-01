---
date: 2024-01-26 03:47:28.610341-07:00
description: "Usar um depurador no Bash significa utilizar ferramentas para testar\
  \ e encontrar problemas nos seus scripts, como capturar bugs que fazem seu c\xF3\
  digo\u2026"
lastmod: '2024-03-13T22:44:46.757158-06:00'
model: gpt-4-0125-preview
summary: "Usar um depurador no Bash significa utilizar ferramentas para testar e encontrar\
  \ problemas nos seus scripts, como capturar bugs que fazem seu c\xF3digo\u2026"
title: Usando um depurador
---

## Como Fazer:
O Bash não vem com um depurador integrado como algumas outras linguagens, mas você pode usar comandos integrados como `set -x` para rastrear o que está acontecendo. Ou, para um upgrade, tem o `bashdb`, um depurador apropriado para percorrer o seu código. Aqui vai uma espiada:

```Bash
# Usando set -x para depurar
set -x
echo "Iniciando a depuração"
my_var="Olá, Mundo da Depuração!"
echo $my_var
set +x

# Usando bashdb
# Instale o bashdb com seu gerenciador de pacotes, por exemplo, apt, yum, brew.
# Depure um script chamado my_script.sh:
bashdb my_script.sh
```

Saída ao executar com `set -x`:
```Bash
+ echo 'Iniciando a depuração'
Iniciando a depuração
+ my_var='Olá, Mundo da Depuração!'
+ echo 'Olá, Mundo da Depuração!'
Olá, Mundo da Depuração!
+ set +x
```

## Mergulho Profundo
Historicamente, depurar scripts Bash significava poluir seu código com declarações `echo`. Mas então veio `set -x`, nos dando uma espiada na execução em tempo real sem impressões manuais. E para aqueles que desejam mais controle, o depurador `bashdb` surgiu, inspirado no depurador gdb para C/C++.

Quanto às alternativas, além dos comandos `set` (`-x`, `-v`, `-e`), outras opções incluem redirecionar a saída para um arquivo para análise ou usar ferramentas externas como ShellCheck para análise estática.

Em termos de implementação, `set -x` é fácil; é uma opção nativa do Bash que imprime comandos e seus argumentos à medida que são executados. `bashdb`, por outro lado, permite percorrer o código, definir pontos de interrupção e avaliar expressões - coisas que lhe dão uma chance de lutar contra bugs mais esquivos.

## Veja Também
- Projeto Bash Debugger: http://bashdb.sourceforge.net/
- "Pro Bash Programming" por Chris Johnson e Jayant Varma para scripts avançados.
- ShellCheck para análise estática: https://www.shellcheck.net/
