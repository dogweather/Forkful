---
title:                "Wyszukiwanie i zamiana tekstu"
date:                  2024-01-20T17:58:15.864864-07:00
model:                 gpt-4-1106-preview
simple_title:         "Wyszukiwanie i zamiana tekstu"
programming_language: "Java"
category:             "Java"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/java/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why? ("Co i Dlaczego?")
Wyszukiwanie i zamiana tekstu to podstawowe operacje umożliwiające zmianę jednego ciągu znaków na inny w obrębie większego tekstu. Programiści robią to często: aby poprawić błędy, zmieniać nazwy czy dostosowywać dane.

## How to: ("Jak to zrobić:")
```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class TextReplaceExample {
    public static void main(String[] args) {
        String originalText = "Jabłka są zielone i jabłka są czerwone.";
        String searchText = "jabłka";
        String replaceWith = "banany";

        // Proste zastąpienie
        String replacedText = originalText.replaceAll(searchText, replaceWith);
        System.out.println(replacedText);
        // Output: Banany są zielone i banany są czerwone.

        // Za pomocą wyrażeń regularnych
        Pattern pattern = Pattern.compile(searchText, Pattern.CASE_INSENSITIVE);
        Matcher matcher = pattern.matcher(originalText);
        String regexReplacedText = matcher.replaceAll(replaceWith);
        System.out.println(regexReplacedText);
        // Output: Banany są zielone i banany są czerwone.
    }
}
```

## Deep Dive ("Dogłębna analiza"):
Zanim pojawiły się wygodne biblioteki i funkcje, taki jak `replaceAll` w Javie, wyszukiwanie i zamiana tekstu wymagały manualnej iteracji po znakach i porównywania znalezionych ciągów. Harsh reality. Teraz to wyjątkowo proste.

Alternatywy? Sprawdź `replace` zamiast `replaceAll` dla prostych, dosłownych zastąpień czy `replaceFirst` żeby zmienić tylko pierwsze wystąpienie. Masz też biblioteki zewnętrzne jak Apache Commons Lang `StringUtils`, jeśli potrzebujesz czegoś bardziej wyspecjalizowanego.

Szczegóły implementacji? `replaceAll` wykorzystuje wyrażenia regularne pod maską, więc jest potężne, ale może być wolniejsze z powodu overheadu kompilacji wyrażeń. Pamiętaj, by używać `Pattern.CASE_INSENSITIVE`, jeśli wielkość liter nie jest istotna.

## See Also ("Zobacz również"):
- [Dokumentacja Oracle – Class Pattern](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/util/regex/Pattern.html)
- [Dokumentacja Oracle – Class String](https://docs.oracle.com/en/java/javase/17/docs/api/java.base/java/lang/String.html)
- [Apache Commons Lang – StringUtils](https://commons.apache.org/proper/commons-lang/javadocs/api-release/org/apache/commons/lang3/StringUtils.html)