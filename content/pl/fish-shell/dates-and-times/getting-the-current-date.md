---
title:                "Pobieranie aktualnej daty"
aliases:
- /pl/fish-shell/getting-the-current-date/
date:                  2024-02-03T19:09:38.513860-07:00
model:                 gpt-4-0125-preview
simple_title:         "Pobieranie aktualnej daty"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/fish-shell/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?
Pobieranie bieżącej daty w programowaniu to podstawowe zadanie, które pozwala na pobieranie i manipulowanie danymi dotyczącymi daty i czasu systemu. W skryptach i zadaniach automatyzacji jest to niezbędne do generowania znaczników czasu, planowania zadań i tworzenia logów.

## Jak to zrobić:
Fish Shell wykorzystuje zewnętrzne polecenia takie jak `date` do pobierania bieżącej daty, oferując elastyczność w formatowaniu wyjścia według potrzeb. Oto jak tego użyć:

```fish
# Wyświetl bieżącą datę w domyślnym formacie
echo (date)

# Przykład wyjścia: Śro 25 Paź 2023 15:42:03 BST
```

Aby dostosować format daty, można użyć opcji `+` po której następują specyfikatory formatu:

```fish
# Wyświetl bieżącą datę w formacie RRRR-MM-DD
echo (date "+%Y-%m-%d")

# Przykład wyjścia: 2023-10-25
```

Do bardziej złożonych zadań, takich jak praca ze znacznikami czasu lub wykonywanie arytmetyki dat, Fish Shell opiera się na zewnętrznych narzędziach takich jak `date` ze względu na jego skryptowy charakter. Oto przykład pobierania bieżącego znacznika czasu UNIX:

```fish
# Pobierz bieżący znacznik czasu UNIX
echo (date "+%s")

# Przykład wyjścia: 1666710123
```

Aby dodać jeden dzień do bieżącej daty za pomocą `date`:

```fish
# Dodaj jeden dzień do bieżącej daty
echo (date -d "+1 day" "+%Y-%m-%d")

# Przykład wyjścia: 2023-10-26
```

Uwaga: Przykłady korzystają z opcji polecenia `date`, które działają z GNU coreutils. Opcje mogą się różnić w innych środowiskach, takich jak macOS, które domyślnie używa polecenia BSD date. Zawsze należy odwoływać się do `date --help` lub strony man, aby uzyskać szczegóły specyficzne dla Twojego środowiska.
