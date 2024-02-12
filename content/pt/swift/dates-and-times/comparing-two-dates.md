---
title:                "Comparando duas datas"
aliases:
- pt/swift/comparing-two-dates.md
date:                  2024-01-20T17:34:00.578172-07:00
model:                 gpt-4-1106-preview
simple_title:         "Comparando duas datas"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/swift/comparing-two-dates.md"
---

{{< edit_this_page >}}

## O Que & Porquê?

Comparar duas datas é um jeito de verificar qual delas vem antes, depois ou se são iguais. Programadores fazem isso para lidar com prazos, eventos e lógicas de tempo em aplicativos.

## Como fazer:

Imagine que você tem duas datas e quer saber qual é a mais recente. No Swift, você usaria `Date()` para criar os objetos de data e depois compará-los usando operadores como `<`, `>` e `==`. Aqui está como isso funciona:

```Swift
import Foundation

let formatter = DateFormatter()
formatter.dateFormat = "dd/MM/yyyy HH:mm"

let date1 = formatter.date(from: "20/03/2023 14:30")!
let date2 = formatter.date(from: "20/03/2023 16:45")!

if date1 < date2 {
    print("A primeira data é mais cedo do que a segunda.")
} else if date1 > date2 {
    print("A primeira data é mais tarde do que a segunda.")
} else {
    print("As datas são iguais.")
}
```

Isso vai imprimir:

```
A primeira data é mais cedo do que a segunda.
```

## Detalhamento:

Swift usa o tipo `Date` para representar pontos específicos no tempo. Comparar datas é um recurso básico, mas vital para coisas como verificar eventos pendentes ou calcular a diferença entre períodos de tempo.

Antes de Swift, em Objective-C e outras linguagens antigas, esse processo era mais complexo e menos intuitivo.

Além de comparar datas com operadores básicos, você pode usar `Calendar` para componentes de data (como dia, mês, ano) e `DateComponents` para representar diferenças de tempo.

## Veja Também:

- Documentação oficial da Apple sobre `Date`: https://developer.apple.com/documentation/foundation/date
- Comparando datas com `Calendar` e `DateComponents`: https://developer.apple.com/documentation/foundation/calendar
- Um guia mais aprofundado sobre DateFormatter: https://developer.apple.com/documentation/foundation/dateformatter
