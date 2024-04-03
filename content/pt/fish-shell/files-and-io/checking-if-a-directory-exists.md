---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:14.988558-07:00
description: "Verificar se um diret\xF3rio existe no Fish Shell permite que scripts\
  \ tomem decis\xF5es com base na presen\xE7a ou aus\xEAncia de estruturas de diret\xF3\
  rios,\u2026"
lastmod: '2024-03-13T22:44:47.020101-06:00'
model: gpt-4-0125-preview
summary: "Verificar se um diret\xF3rio existe no Fish Shell permite que scripts tomem\
  \ decis\xF5es com base na presen\xE7a ou aus\xEAncia de estruturas de diret\xF3\
  rios, possibilitando tarefas como opera\xE7\xF5es condicionais de arquivos, registro\
  \ em logs ou configura\xE7\xE3o do ambiente."
title: "Verificando se um diret\xF3rio existe"
weight: 20
---

## Como fazer:
O Fish Shell utiliza o comando `test` para verificar tipos de arquivos e características, incluindo se um alvo é um diretório. Aqui está um padrão básico para verificar se um diretório existe:

```fish
if test -d /caminho/para/dir
    echo "O diretório existe"
else
    echo "O diretório não existe"
end
```
Saída de Exemplo:
```
O diretório existe
```

Para operações de arquivos e diretórios mais simplificadas, pode-se recorrer a ferramentas externas como `fd`, embora seja mais comumente usado para encontrar arquivos e diretórios em vez de apenas verificar a existência. No entanto, combiná-lo com scripts Fish pode produzir resultados úteis:

```fish
set dir "/caminho/para/pesquisar"
if fd . $dir --type directory --max-depth 1 | grep -q $dir
    echo "O diretório existe"
else
    echo "O diretório não existe"
end
```

Este exemplo com `fd` procura pelo diretório em uma profundidade especificada, e o `grep` verifica a correspondência, tornando-o versátil para verificações nuances. Contudo, para o propósito direto de verificar a existência, apegar-se ao `test` integrado do Fish é tanto eficiente quanto direto.
