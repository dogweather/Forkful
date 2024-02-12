---
title:                "Pisanie do standardowego błędu"
date:                  2024-02-03T19:32:53.775582-07:00
model:                 gpt-4-0125-preview
simple_title:         "Pisanie do standardowego błędu"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/cpp/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Pisanie do standardowego błędu (`stderr`) w C++ polega na wyprowadzaniu komunikatów o błędach lub diagnostyki, które są oddzielone od głównego wyniku działania programu. Programiści robią to, aby skierować błędy do innego strumienia, co umożliwia łatwiejsze debugowanie i obsługę błędów poprzez rozróżnienie normalnego wyniku od komunikatów o błędach.

## Jak to zrobić:

W C++, pisanie do standardowego błędu można osiągnąć za pomocą strumienia `cerr`, który jest częścią standardowej biblioteki. Oto podstawowy przykład:

```cpp
#include <iostream>

int main() {
    // Pisanie do standardowego wyjścia
    std::cout << "To jest zwykła wiadomość." << std::endl;
    
    // Pisanie do standardowego błędu
    std::cerr << "To jest wiadomość o błędzie." << std::endl;
    
    return 0;
}
```

Przykładowe wyjście:
```
To jest zwykła wiadomość.
To jest wiadomość o błędzie.
```

W tym przypadku obie wiadomości zwykle pojawią się na twoim terminalu, ale możesz je przekierować oddzielnie w powłoce. Na przykład, można wysłać standardowe wyjście do pliku, jednocześnie pozwalając, aby błędy były wyświetlane na ekranie.

Do bardziej zaawansowanego rejestrowania i obsługi błędów można użyć bibliotek stron trzecich, takich jak `spdlog` lub `boost.log`. Te biblioteki oferują zaawansowane funkcje do rejestrowania, w tym formatowanie, poziomy logowania i wyjście do pliku.

Oto jak możesz użyć `spdlog` do zapisania wiadomości o błędzie:

```cpp
#include "spdlog/spdlog.h"

int main() {
    // Inicjalizacja spdlog
    spdlog::info("To jest zwykła wiadomość.");
    spdlog::error("To jest wiadomość o błędzie.");
    
    return 0;
}
```

Uwaga: Aby użyć `spdlog`, musisz dodać go do swojego projektu. Możesz to zrobić klonując repozytorium z GitHuba lub używając menedżera pakietów jak `vcpkg` lub `conan`.

Pamiętaj, wybór między bezpośrednim używaniem strumieni standardowych a biblioteką taką jak `spdlog` zależy od złożoności twojej aplikacji i twoich konkretnych potrzeb dotyczących obsługi błędów i rejestrowania.
