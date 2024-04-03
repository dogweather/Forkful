---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:56.753496-07:00
description: "Wyra\u017Cenia regularne w programowaniu umo\u017Cliwiaj\u0105 dopasowywanie\
  \ wzorc\xF3w i manipulowanie ci\u0105gami znak\xF3w na podstawie okre\u015Blonych\
  \ wzor\xF3w. Programi\u015Bci u\u017Cywaj\u0105\u2026"
lastmod: '2024-03-13T22:44:35.529995-06:00'
model: gpt-4-0125-preview
summary: "Wyra\u017Cenia regularne w programowaniu umo\u017Cliwiaj\u0105 dopasowywanie\
  \ wzorc\xF3w i manipulowanie ci\u0105gami znak\xF3w na podstawie okre\u015Blonych\
  \ wzor\xF3w."
title: "Korzystanie z wyra\u017Ce\u0144 regularnych"
weight: 11
---

## Jak to zrobić:
Lua nie obsługuje natywnie wyrażeń regularnych w ten sam sposób co języki takie jak Perl czy Python. Zamiast tego oferuje możliwości dopasowywania wzorców, które pokrywają wiele powszechnych przypadków użycia wyrażeń regularnych. Jednakże, w przypadku potrzeby pełnoprawnego wsparcia wyrażeń regularnych, można użyć biblioteki firm trzecich, takiej jak `lrexlib`.

### Podstawowe dopasowywanie wzorców w Lua:
Lua zapewnia potężny system dopasowywania wzorców, którego możesz użyć do prostych zamienników i wyszukiwań:

```lua
-- Proste wyszukiwanie
local str = "Hello, World!"
if string.find(str, "World") then
  print("Znaleziono dopasowanie!")
end
-- Wynik: Znaleziono dopasowanie!

-- Prosta zamiana
local s = string.gsub("Lua jest świetna!", "świetna", "niesamowita")
print(s)
-- Wynik: Lua jest niesamowita!
```

### Przechwytywanie podciągów:
Możesz przechwycić części ciągu, które pasują do wzorców:

```lua
local date = "Dzisiaj jest 17/05/2023."
local d, m, y = string.match(date, "(%d+)/(%d+)/(%d+)")
print("Dzień:", d, "Miesiąc:", m, "Rok:", y)
-- Wynik: Dzień: 17 Miesiąc: 05 Rok: 2023
```

### Użycie `lrexlib` do wyrażeń regularnych:
Aby użyć rzeczywistych wyrażeń regularnych, możesz zainstalować i użyć `lrexlib`. Zakładając, że masz to zainstalowane (`luarocks install lrexlib-pcre`), możesz wykonać bardziej złożone dopasowywanie wzorców:

```lua
local rex = require 'rex_pcre'

local text = "Deszcz w Hiszpanii pada głównie na równinach."
local regex = "\\bS\\w+"
local count, err = rex.gsub(text, regex, function(w)
  return w:upper()
end)
if err then
  print("Błąd:", err)
else
  print("Zmodyfikowany tekst:", text)
  print("Dokonane zamiany:", count)
end
-- Przykładowy wynik: Zmodyfikowany tekst: Deszcz w Hiszpanii pada głównie na równinach.
-- Dokonane zamiany: 3
```

Powyższe przykłady ilustrują podstawowe użycie systemu dopasowywania wzorców w Lua i jak wykorzystać moc wyrażeń regularnych za pomocą `lrexlib`. Niezależnie od tego, czy wykonujesz proste manipulacje ciągami znaków, czy wymagasz pełnej wszechstronności wyrażeń regularnych, Lua w połączeniu z potężnymi bibliotekami może zaspokoić Twoje potrzeby.
