---
date: 2024-01-20 17:37:07.446385-07:00
description: "Converter uma data para uma string significa transform\xE1-la de um\
  \ formato de data, como UNIX Timestamp ou DateTime, para uma sequ\xEAncia de caracteres\u2026"
lastmod: '2024-03-13T22:44:46.678678-06:00'
model: gpt-4-1106-preview
summary: "Converter uma data para uma string significa transform\xE1-la de um formato\
  \ de data, como UNIX Timestamp ou DateTime, para uma sequ\xEAncia de caracteres\
  \ leg\xEDveis."
title: Convertendo uma data em uma string
weight: 28
---

## How to:
Vamos direto ao ponto: você precisa exibir ou salvar uma data em um formato personalizado em PHP? Use a classe `DateTime` e o método `format`. Aqui está como.

```PHP
<?php
$data = new DateTime('now', new DateTimeZone('Europe/Lisbon'));
echo $data->format('d/m/Y H:i:s'); // saída: 15/03/2023 14:23:08
?>
```

Nota: `d/m/Y H:i:s` é um formato comum em Portugal, com dia, mês, ano, hora, minutos e segundos.

## Deep Dive
Desde os primórdios do PHP, lidar com datas era possível, mas nem sempre direto. A função `date()` era a go-to para muitos desenvolvedores, mas tinha suas limitações, especialmente em relação a fusos horários e cálculos de data.

Com o PHP 5.2.0, veio o `DateTime`, uma melhoria monumental. Ele oferece orientação a objetos, manipulação de fuso horário e comparação de datas. Outra opção é o `DateTimeImmutable`, que, como o nome indica, retorna um objeto imutável sempre que você modifica a data.

Manejar fusos horários é fácil com `DateTime`. Basta passar o fuso desejado como parâmetro no construtor.

Alternativa tradicional: usar `date()` e `strtotime()`.

```PHP
echo date('d/m/Y H:i:s', strtotime('now')); // mesma saída anterior
```

Mas seja cauteloso — `strtotime()` pode fazer mágicas com strings em inglês, mas não necessariamente entenderá outros idiomas com a mesma facilidade.

## See Also
Para mergulhar fundo nas possibilidades de `DateTime` e `DateTimeImmutable`, confira a documentação oficial do PHP:

- [DateTime](https://www.php.net/manual/pt_BR/class.datetime.php)
- [DateTimeImmutable](https://www.php.net/manual/pt_BR/class.datetimeimmutable.php)

E para entender todos os formatos de saída possíveis com o método `format`:

- [Date/Time Formats](https://www.php.net/manual/pt_BR/datetime.format.php)

Espero que isso torne sua vida com PHP e datas um pouquinho mais fácil!
