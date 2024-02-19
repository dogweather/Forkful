---
aliases:
- /pl/cpp/using-regular-expressions/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:16:34.423624-07:00
description: "Wyra\u017Cenia regularne w C++ to sekwencje znak\xF3w definiuj\u0105\
  ce wzorzec wyszukiwania, u\u017Cywane do dopasowywania lub manipulacji ci\u0105\
  gami znak\xF3w. Programi\u015Bci\u2026"
lastmod: 2024-02-18 23:08:49.900008
model: gpt-4-0125-preview
summary: "Wyra\u017Cenia regularne w C++ to sekwencje znak\xF3w definiuj\u0105ce wzorzec\
  \ wyszukiwania, u\u017Cywane do dopasowywania lub manipulacji ci\u0105gami znak\xF3\
  w. Programi\u015Bci\u2026"
title: "Korzystanie z wyra\u017Ce\u0144 regularnych"
---

{{< edit_this_page >}}

## Co i dlaczego?
Wyrażenia regularne w C++ to sekwencje znaków definiujące wzorzec wyszukiwania, używane do dopasowywania lub manipulacji ciągami znaków. Programiści używają ich do zadań takich jak walidacja danych wejściowych, wyszukiwanie wystąpień w ciągach znaków czy dzielenie ciągów na tokeny, co czyni je niezbędnym narzędziem dla efektywnej i skutecznej obróbki tekstu.

## Jak to zrobić:
C++11 wprowadziło wsparcie dla wyrażeń regularnych w bibliotece standardowej, `<regex>`, oferując solidne ramy do wyszukiwania i manipulacji ciągami znaków. Oto podstawowy przykład użycia wyrażeń regularnych do wyszukiwania wzorca w ciągu znaków:

```cpp
#include <iostream>
#include <regex>

int main() {
    std::string target = "Hello, my email is example@example.com";
    std::regex email_pattern(R"(\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b)");

    if (std::regex_search(target, email_pattern)) {
        std::cout << "Email znaleziony!" << std::endl;
    } else {
        std::cout << "Nie znaleziono adresu email." << std::endl;
    }

    return 0;
}
```
**Przykładowe wyjście**
```
Email znaleziony!
```

Do bardziej złożonych manipulacji, takich jak zastępowanie wzorców w ciągach, wyrażenia regularne w C++ mogą być bardzo przydatne:

```cpp
#include <iostream>
#include <regex>

int main() {
    std::string text = "W Hiszpanii deszcz pada głównie na równinach.";
    std::regex vowel_regex("([aeiou])");

    std::string replaced_text = std::regex_replace(text, vowel_regex, "*");
    std::cout << replaced_text << std::endl;

    return 0;
}
```
**Przykładowe wyjście**
```
W H*szp*n** d*szcz p*d* gł*wn** n* r*wn*n*ch.
```

Dla programistów szukających rozwiązań poza biblioteką standardową, biblioteka Boost Regex (`boost/regex.hpp`) jest popularną opcją zewnętrzną oferującą zwiększone możliwości i optymalizacje wydajności, szczególnie dla złożonych wzorców lub obszernej obróbki danych:

```cpp
#include <iostream>
#include <boost/regex.hpp>

int main() {
    std::string s = "Biblioteki Boost są fajne!";
    boost::regex expr("(\\w+)\\s(biblioteki)"); // Dopasuj "Biblioteki Boost"
    std::string fmt("GNU \\1"); // Zastąp "GNU Boost"

    std::string result = boost::regex_replace(s, expr, fmt);
    std::cout << result << std::endl;

    return 0;
}
```
**Przykładowe wyjście**
```
GNU Boost są fajne!
```

Te przykłady tylko naruszają powierzchnię możliwości C++ z wyrażeniami regularnymi, ilustrując podstawowe wyszukiwania, dopasowywanie wzorców i zastępowania, używając albo biblioteki standardowej, albo wzmocnione przez potężną implementację wyrażeń regularnych Boost.
