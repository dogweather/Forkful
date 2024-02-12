---
title:                "Arredondamento de números"
aliases:
- pt/bash/rounding-numbers.md
date:                  2024-01-26T03:42:45.205559-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arredondamento de números"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/bash/rounding-numbers.md"
---

{{< edit_this_page >}}

## O Que e Por Quê?

Arredondar números significa cortar os decimais para um valor mais simples que seja suficiente para um determinado contexto. Programadores arredondam números para simplificar resultados, economizar espaço ou porque o valor exato não é vital — como quando você está estimando o uso da CPU ou espaço em disco, e os decimais não vão fazer ou desfazer o seu dia.

## Como Fazer:

Aqui está o essencial sobre arredondamento no Bash:

```Bash
# Arredondar para baixo usando 'floor' com bc
echo "scale=0; 3.49/1" | bc

# Arredondar para cima usando 'ceiling' com bc
echo "scale=0; 3.01/1" | bc -l

# Arredondar para o inteiro mais próximo usando printf
printf "%.0f\n" 3.49

# Um truque para arredondar para o inteiro mais próximo usando bc
echo "(3.49+0.5)/1" | bc
```

Saídas de exemplo — direto da boca do terminal:

```
3  # Arredondado para baixo (floor)
4  # Arredondado para cima (ceiling)
3  # Arredondado para o mais próximo (com printf)
3  # Arredondado para o mais próximo (com bc)
```

## Aprofundamento

Nos velhos tempos, não havia `bc` ou `printf` em scripts Bash para fazer a mágica matemática. Os mais antigos tinham que contar com ferramentas externas ou soluções engenhosas. Agora, `bc` permite fazer matemática com precisão. Tenha em mente, `bc` não arredonda por padrão — ele faz o floor. A parte do scale define a ação do ponto decimal.

Alternativas? Você poderia usar `awk` para arredondar sem mudar para `bc` ou lidar com `perl` para necessidades matemáticas mais pesadas. Para os masoquistas, vá de Bash puro com, digamos, manipulação de strings iterativa – mas por quê?

Quanto aos detalhes, `bc` não apenas arredonda, ele faz um monte de coisas matemáticas — escalona, faz seno, raiz quadrada, você escolhe. Com `printf`, é mais sobre formatação de texto, mas ei, ele arredonda números, então não estamos reclamando.

## Veja Também

Para aqueles com fome de mais:

- Manual do GNU `bc`: https://www.gnu.org/software/bc/manual/html_mono/bc.html
- Comando Bash `printf`: https://www.gnu.org/software/bash/manual/html_node/Bash-Builtins.html#index-printf
- Guia do usuário AWK (para arredondamento e outros processamentos de texto): https://www.gnu.org/software/gawk/manual/gawk.html
- Mais matemática Bash, scripts e truques com números: https://mywiki.wooledge.org/BashFAQ/022
