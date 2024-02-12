---
title:                "Korzystanie z tablic asocjacyjnych"
aliases:
- pl/lua/using-associative-arrays.md
date:                  2024-01-30T19:12:07.716226-07:00
model:                 gpt-4-0125-preview
simple_title:         "Korzystanie z tablic asocjacyjnych"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/lua/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i Dlaczego?

Tablice asocjacyjne to jak tajne uściski dłoni dla danych w Lua — zamiast samych numerów ustawiających się posłusznie według indeksu, Twoje klucze mogą być czymkolwiek chcesz, co sprawia, że odzyskiwanie danych jest dziecinnie proste. Dlaczego programiści ich używają? Ponieważ czasami trzeba wywołać kawałek danych po jego nazwie, a nie po numerze w kolejności.

## Jak to zrobić:

W Lua, tworzenie tablicy asocjacyjnej (lub tabeli, jak mówią w Lua) jest proste. Rezygnujesz z typowych numerycznych indeksów na rzecz własnych kluczy. Spójrz na to:

```Lua
-- Tworzenie tablicy asocjacyjnej
userInfo = {
  name = "Jamie",
  occupation = "Awangardzista",
  level = 42
}

-- Dostęp do elementów
print(userInfo["name"]) -- Drukuje Jamie
print(userInfo.occupation) -- Drukuje Awangardzista

-- Dodawanie nowych par klucz-wartość
userInfo["hobby"] = "Kodowanie"
userInfo.favLang = "Lua"

-- Iteracja po tablicy asocjacyjnej
for key, value in pairs(userInfo) do
  print(key .. ": " .. value)
end
```

Wynik:
```
Jamie
Awangardzista
name: Jamie
occupation: Awangardzista
level: 42
hobby: Kodowanie
favLang: Lua
```

Fajna sprawa? Wchodzisz w interakcję z danymi za pomocą kluczy, które mają dla Ciebie znaczenie, co sprawia, że kod jest czytelniejszy i łatwiejszy w utrzymaniu.

## Wnikliwe spojrzenie

Kiedy Lua pojawiła się na scenie, wprowadziła tabele jako uniwersalną strukturę danych, rewolucjonizując sposób, w jaki deweloperzy zarządzają danymi. W przeciwieństwie do niektórych języków, gdzie tablice asocjacyjne i tablice są odrębnymi bytami, tabele w Lua służą jako oba typy, upraszczając krajobraz struktur danych.

To, co sprawia, że tabele Lua są szczególnie potężne, to ich elastyczność. Jednak ta elastyczność ma swoją cenę w postaci potencjalnych konsekwencji wydajnościowych, szczególnie przy dużych zbiorach danych, gdzie bardziej wyspecjalizowana struktura danych może być preferowana dla efektywności.

Chociaż Lua natywnie nie obsługuje bardziej konwencjonalnych struktur danych „od ręki”, takich jak listy wiązane czy mapy mieszające, dostosowalność struktury tabeli oznacza, że możesz je zaimplementować przy użyciu tabel, jeśli potrzebujesz. Pamiętaj tylko: z wielką mocą wiąże się wielka odpowiedzialność. Używaj elastyczności rozsądnie, aby zachować wydajność i czytelność kodu.
