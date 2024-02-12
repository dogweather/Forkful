---
title:                "Praca z JSON"
aliases:
- pl/c/working-with-json.md
date:                  2024-02-03T18:12:08.801332-07:00
model:                 gpt-4-0125-preview
simple_title:         "Praca z JSON"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/c/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Praca z JSON (JavaScript Object Notation) w języku C obejmuje parsowanie, generowanie i manipulowanie strukturami danych JSON. Programiści robią to, aby umożliwić komunikację z serwisami internetowymi, przechowywaniem danych lub plikami konfiguracyjnymi w lekkim i czytelnym dla człowieka formacie.

## Jak to zrobić:

Aby pracować z JSON w C, zazwyczaj używa się biblioteki takiej jak `jansson` lub `json-c` ze względu na brak wbudowanego wsparcia w C dla JSON. Tutaj skupimy się na `jansson` ze względu na łatwość użycia i aktywne utrzymanie. Najpierw zainstaluj bibliotekę (np. używając menedżera pakietów jak `apt` na Ubuntu: `sudo apt-get install libjansson-dev`).

Zacznijmy od parsowania łańcucha JSON i dostępu do jego zawartości:

```c
#include <jansson.h>
#include <stdio.h>

int main() {
    const char *json_string = "{\"name\":\"John Doe\",\"age\":30}";
    json_error_t error;
    json_t *root = json_loads(json_string, 0, &error);
    
    if(!root) {
        fprintf(stderr, "error: on line %d: %s\n", error.line, error.text);
        return 1;
    }
    
    const char *name;
    int age;
    json_unpack(root, "{s:s, s:i}", "name", &name, "age", &age);
    
    printf("Imię: %s\nWiek: %d\n", name, age);
    
    json_decref(root);
    return 0;
}
```

Przykładowe wyjście:
```
Imię: John Doe
Wiek: 30
```

Następnie, tworzenie i wyprowadzanie obiektu JSON:

```c
#include <jansson.h>
#include <stdio.h>

int main() {
    json_t *root = json_object();
    json_object_set_new(root, "name", json_string("Jane Doe"));
    json_object_set_new(root, "age", json_integer(25));
    
    char *json_dump = json_dumps(root, JSON_ENCODE_ANY);
    printf("%s\n", json_dump);
    
    free(json_dump);
    json_decref(root);
    return 0;
}
```

Przykładowe wyjście:
```
{"name": "Jane Doe", "age": 25}
```

Te przykłady demonstrują podstawy ładowania łańcucha JSON, rozpakowywania jego wartości, tworzenia nowego obiektu JSON i następnie wyprowadzania go jako łańcucha.

## Pogłębiona analiza

Potrzeba pracy z JSON w C wynika z przyjęcia JSON przez internet jako głównego formatu wymiany danych. Prostota i efektywność JSON szybko sprawiły, że wyprzedził on XML, pomimo początkowego braku bezpośredniego wsparcia w C dla manipulacji JSON. Wczesne rozwiązania obejmowały ręczną manipulację łańcuchami - narażone na błędy i nieefektywne. Biblioteki takie jak `jansson` i `json-c` pojawiły się, aby wypełnić tę lukę, oferując rozbudowane API do parsowania, konstruowania i serializacji JSON.

Chociaż `jansson` oferuje prostotę i łatwość użycia, `json-c` może przyciągnąć tych, którzy szukają szerszego zestawu funkcji. Niemniej jednak, alternatywy, takie jak biblioteki parsujące w C++ oferują bardziej zaawansowane abstrakcje, dzięki bardziej złożonym strukturom danych tego języka i wsparciu biblioteki standardowej. Jednakże, gdy pracuje się w środowiskach, gdzie C jest preferowanym lub wymaganym językiem - takich jak systemy wbudowane lub podczas łączenia się z istniejącymi bibliotekami C - używanie `jansson` lub `json-c` staje się niezbędne.

Warto również zauważyć, że praca z JSON w C wiąże się z głębszym zrozumieniem zarządzania pamięcią, ponieważ te biblioteki często zwracają dynamicznie alokowane obiekty, które wymagają jawnej dealokacji. Stawia to programistów przed wyzwaniem zrównoważenia wygody z odpowiedzialnością za zapobieganie wyciekom pamięci, kluczowym aspektem tworzenia wydajnego kodu C.
