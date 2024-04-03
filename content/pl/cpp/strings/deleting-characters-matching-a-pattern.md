---
date: 2024-01-20 17:41:48.198353-07:00
description: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca to po prostu czyszczenie\
  \ tekst\xF3w z niepotrzebnych fragment\xF3w. Programi\u015Bci robi\u0105 to, by\
  \ u\u0142atwi\u0107 przetwarzanie danych,\u2026"
lastmod: '2024-03-13T22:44:35.697067-06:00'
model: gpt-4-1106-preview
summary: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca to po prostu czyszczenie tekst\xF3\
  w z niepotrzebnych fragment\xF3w."
title: "Usuwanie znak\xF3w pasuj\u0105cych do wzorca"
weight: 5
---

## How to: (Jak to zrobić:)
```C++
#include <iostream>
#include <string>
#include <regex>

std::string delete_matching_chars(std::string str, const std::string& pattern) {
    std::regex reg(pattern);
    return std::regex_replace(str, reg, "");
}

int main() {
    std::string data = "Cześć! Moje nr telefonu to 123-456-789, a email to example@domain.com";
    std::string pattern = "\\d"; // Usunięcie wszystkich cyfr
    std::string result = delete_matching_chars(data, pattern);
    std::cout << result << std::endl; // Output: Cześć! Moje nr telefonu to ---, a email to example@domain.com
    return 0;
}
```

## Deep Dive (Wgłębiając się)
Usuwanie pasujących znaków jest tak stare jak same wyrażenia regularne, które pojawiły się w latach 50. XX wieku. Są różne sposoby, np. iteracja po każdym znaku i sprawdzenie czy pasuje do wzoru. Wyrażenia regularne to jednak szybsze i bardziej elastyczne rozwiązanie.

Wiele języków ma własne wersje wyrażeń regularnych, jednak C++ stosuje bibliotekę `<regex>` obecną od C++11. Wcześniej używano zewnętrznych bibliotek, jak Boost.Regex. Alternatywą jest też ręczne tworzenie funkcji do przeszukiwania i zmiany danych, co może być szybsze dla prostych wzorców, lecz znacząco mniej czytelne i trudne w utrzymaniu.

## See Also (Zobacz również)
- [cppreference.com: std::regex](https://en.cppreference.com/w/cpp/regex)
- [Regular Expressions in C++ (cpluplus.com)](http://www.cplusplus.com/reference/regex/)
- [Boost.Regex documentation](https://www.boost.org/doc/libs/1_75_0/libs/regex/doc/html/index.html)
