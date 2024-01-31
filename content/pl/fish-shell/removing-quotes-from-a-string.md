---
title:                "Usuwanie cudzysłowów z ciągu znaków"
date:                  2024-01-26T03:39:16.776497-07:00
model:                 gpt-4-0125-preview
simple_title:         "Usuwanie cudzysłowów z ciągu znaków"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/fish-shell/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## Co i dlaczego?

Usuwanie cudzysłowów z ciągu znaków polega na pozbyciu się tych irytujących pojedynczych (' ') lub podwójnych (" ") znaków cudzysłowu z danych tekstowych. Programiści często robią to, aby oczyścić dane wejściowe lub przygotować dane do dalszej obróbki bez bałaganu związanego z cudzysłowami.

## Jak to zrobić:

Fish ma wbudowane czary do tego rodzaju zadań. Użyj funkcji `string` bez większego wysiłku. Sprawdź te zaklęcia:

```fish
# Przykład z pojedynczymi cudzysłowami
set quoted "'Hello, World!'"
set unquoted (string trim --chars \"\'\" $quoted)
echo $unquoted # Wyjście: Hello, World!

# To samo dotyczy podwójnych cudzysłowów
set double_quoted "\"Hello, Universe!\""
set unquoted (string trim --chars \"\'\" $double_quoted)
echo $unquoted # Wyjście: Hello, Universe!
```

## Dogłębna eksploracja

W kamiennej erze linii poleceń musiałbyś zmagać się z `sed` lub `awk`, aby usunąć cudzysłowy; prawdziwy gąszcz ukośników wstecznych i tajemniczych flag. Funkcja `string` w Fish pochodzi z nowszej ery, sprawiając, że kod jest czyściejszy i bardziej intuicyjny.

Alternatywy w innych powłokach mogą nadal polegać na tych starych narzędziach lub mogą używać własnych wbudowanych metod, takich jak ekspansja parametrów w bashu czy modyfikatory w zsh.

Funkcja `string` wykracza poza same przycinanie cudzysłowów. To scyzoryk Szwajcarski do operacji na ciągach znaków w Fish. Dzięki `string`, możesz ciąć, dzielić, łączyć czy nawet dopasowywać wyrażenia regularne bezpośrednio w terminalu.

## Zobacz także

Pogłęb swoją wiedzę o `string` z pomocą oficjalnej dokumentacji:
- [Dokumentacja Fish Shell String](https://fishshell.com/docs/current/commands.html#string)

Do nostalgii lub kiedy piszesz skrypty w bardziej tradycyjnych powłokach, sprawdź:
- [Przewodnik po Sed & Awk](https://www.grymoire.com/Unix/Sed.html)
- [Ekspansja Parametrów w Bash](https://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html)
