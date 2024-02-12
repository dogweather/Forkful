---
title:                "Pobieranie aktualnej daty"
aliases:
- pl/bash/getting-the-current-date.md
date:                  2024-02-03T19:09:00.408037-07:00
model:                 gpt-4-0125-preview
simple_title:         "Pobieranie aktualnej daty"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/bash/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?
Pobieranie aktualnej daty w Bashu polega na używaniu wbudowanych poleceń do wyświetlania daty i czasu w różnych formatach. Programiści używają tej funkcjonalności do zadań takich jak dodawanie znaczników czasowych do logów, planowanie zadań lub po prostu jako część swoich skryptów informacji systemowych, aby śledzić, kiedy wykonano akcje.

## Jak to zrobić:
W Bashu polecenie `date` jest twoim głównym narzędziem do pobierania aktualnej daty i czasu. Oto kilka przykładów, jak można go używać:

1. **Pobierz aktualną datę i czas w domyślnym formacie:**

```bash
date
```

*Przykładowe wyjście:*
```
Śro, 5 kwi 14:22:04 PDT 2023
```

2. **Dostosuj format wyjściowy:** Możesz określić format wyjściowy, używając specyfikatorów formatu `+%`. Na przykład, aby wyświetlić datę w formacie RRRR-MM-DD:

```bash
date "+%Y-%m-%d"
```

*Przykładowe wyjście:*
```
2023-04-05
```

3. **Pobierz aktualną sygnaturę czasową UNIX:** Sygnatura czasowa UNIX to liczba sekund od Epoki UNIX (1 stycznia 1970). Jest to przydatne dla skryptów, które wykonują obliczenia oparte na różnicach czasowych.

```bash
date "+%s"
```

*Przykładowe wyjście:*
```
1672877344
```

Do tej podstawowej operacji w Bashu zazwyczaj nie używa się popularnych bibliotek firm trzecich, ponieważ wbudowane polecenie `date` zapewnia obszerną funkcjonalność. Jednakże, do bardziej zaawansowanych manipulacji datą i czasem, programiści mogą używać innych języków programowania lub narzędzi oferujących biblioteki do arytmetyki i analizy dat, takie jak moduł `datetime` w Pythonie.
