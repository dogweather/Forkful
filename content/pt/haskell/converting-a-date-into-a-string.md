---
title:                "Convertendo uma data em uma string"
date:                  2024-01-20T17:36:43.690529-07:00
model:                 gpt-4-1106-preview
simple_title:         "Convertendo uma data em uma string"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/haskell/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## O Que & Porquê?
Converter uma data em uma string significa transformar a representação de uma data, normalmente numa estrutura de dados específica, para um formato de texto legível. Fazemos isso para facilitar a exibição de datas para usuários, armazenar em formatos compatíveis com texto, ou para manipulações em sistemas que não reconhecem tipos de data específicos.

## Como fazer:
```haskell
import Data.Time

-- Convertendo a data atual em uma string
main :: IO ()
main = do
    -- Pega a data e hora atual
    currentDateTime <- getCurrentTime

    -- Converte a data/hora em uma string formatada (yyyy-mm-dd)
    let dateString = formatTime defaultTimeLocale "%Y-%m-%d" currentDateTime

    -- Mostra a string formatada
    putStrLn dateString
```

Sample output:
```
2023-03-15
```

## Aprofundando
Converter datas em strings está diretamente associado aos primeiros dias da computação quando a manipulação e armazenamento de datas era complicado devido ao formato binário. Com o tempo, surgiram bibliotecas padrão em várias linguagens, como o `Data.Time` em Haskell, para simplificar o processo.

Existem alternativas para formatar datas em Haskell, incluindo bibliotecas externas como `time-fmt` que podem oferecer mais opções personalizadas. No entanto, o `Data.Time` é a escolha padrão por ser amplamente suportado e funcional.

Os detalhes da implementação envolvem o uso de locales (`defaultTimeLocale` no exemplo) que definem a representação de texto da data e hora de acordo com a localidade e a cultura. Isso é útil para internacionalização.

## Veja também
- Haskell 'time' library documentation: [Hackage Time](https://hackage.haskell.org/package/time)
- Time formatting in Haskell: [Formatting Time and Date in Haskell](https://two-wrongs.com/haskell-time-library-tutorial)
