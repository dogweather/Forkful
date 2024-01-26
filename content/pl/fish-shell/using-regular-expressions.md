---
title:                "Wykorzystanie wyrażeń regularnych"
html_title:           "Arduino: Wykorzystanie wyrażeń regularnych"
simple_title:         "Wykorzystanie wyrażeń regularnych"
programming_language: "Fish Shell"
category:             "Fish Shell"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/fish-shell/using-regular-expressions.md"
---

{{< edit_this_page >}}

## What & Why? - Co i dlaczego?
Wyrażenia regularne to wzorce używane do wyszukiwania i manipulowania tekstami. Programiści używają ich, bo pozwalają na zaawansowane przetwarzanie tekstu niewielkim kosztem.

## How to: - Jak to zrobić:
Znajdowanie słów zaczynających się na "pl" w pliku `tekst.txt`:

```Fish Shell
grep '^pl' tekst.txt
```

Zastępowanie "fish" słowem "shell" w `skrypt.fish`:

```Fish Shell
sed 's/fish/shell/g' skrypt.fish > skrypt_zmieniony.fish
```

Wyszukiwanie wszystkich plików `.fish` wyświetlając linie pasujące do wzorca "function":

```Fish Shell
grep 'function' *.fish
```

## Deep Dive - Zagłębienie się
Wyrażenia regularne powstały w latach 50, kiedy to Stephen Cole Kleene opisał teoretyczny model zwany "regular expressions". Obecnie istnieje wiele odmian, np. POSIX czy Perl-Compatible Regular Expressions (PCRE), a każda implementacja ma swoje unikalne cechy. W skorupce Fish zazwyczaj korzysta się z narzędzi jak `grep`, `sed`, `awk`, które używają regular expressions w sposób charakterystyczny dla systemu Unix.

## See Also - Zobacz też
Dokumentacja `grep`: https://www.gnu.org/software/grep/manual/grep.html

Dokumentacja `sed`: https://www.gnu.org/software/sed/manual/sed.html

Tutorial wyrażeń regularnych: https://www.regular-expressions.info/tutorial.html

Podręcznik skorupki Fish: https://fishshell.com/docs/current/index.html
