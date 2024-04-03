---
date: 2024-01-27 20:33:56.363464-07:00
description: "Generowanie losowych liczb jest podstawowym zadaniem w programowaniu,\
  \ u\u017Cywanym do wszystkiego - od pr\xF3bkowania danych po rozw\xF3j gier. W Fish\
  \ Shell u\u017Cycie\u2026"
lastmod: '2024-03-13T22:44:35.834760-06:00'
model: gpt-4-0125-preview
summary: "Generowanie losowych liczb jest podstawowym zadaniem w programowaniu, u\u017C\
  ywanym do wszystkiego - od pr\xF3bkowania danych po rozw\xF3j gier."
title: Generowanie liczb losowych
weight: 12
---

## Jak to zrobić:
Generowanie losowej liczby w Fish może być proste, przy użyciu kombinacji narzędzi systemowych i możliwości powłoki. Poniżej znajdują się przykłady demonstrujące, jak generować losowe liczby w określonych zakresach.

**Generowanie losowej liczby między 0 a 100:**

```fish
set -l rand_num (random 0 100)
echo $rand_num
```

**Przykładowy wynik:**
```fish
42
```

**Generowanie losowej liczby między dowolnymi dwoma liczbami, powiedzmy 50 i 150:**

```fish
set -l min 50
set -l max 150
set -l rand_num (random $min $max)
echo $rand_num
```

**Przykładowy wynik:**
```fish
103
```

**Używanie random do mieszania listy:**

Możesz także chcieć losowo przetasować elementy na liście. Oto jak możesz to zrobić:

```fish
set -l my_list A B C D E
random (seq (count $my_list)) | while read i
    echo $my_list[$i]
end
```

**Przykładowy wynik:**
```fish
C
A
E
D
B
```

Zwróć uwagę, że wynik będzie się różnić za każdym razem, gdy uruchomisz te komendy z powodu natury losowości.

## Głębsze spojrzenie
Funkcja `random` w Fish Shell zapewnia łatwy w użyciu interfejs do generowania liczb pseudolosowych. Wewnętrznie opakowuje ona narzędzia systemowe do generowania liczb losowych, oferując przenośny sposób na wprowadzenie losowości do skryptów. Jednakże, ważne jest, aby pamiętać, że losowość zapewniana przez `random` jest wystarczająca dla większości zadań skryptowych, ale może nie spełniać wymagań bezpieczeństwa kryptograficznego dla aplikacji wymagających wyższego stopnia nieprzewidywalności.

Dla kontekstów bezpieczeństwa o wysokich stawkach, rozważ użycie dedykowanych narzędzi lub bibliotek programistycznych zaprojektowanych dla celów kryptograficznych, które zapewniają mocniejsze gwarancje losowości. Niemniej jednak, dla ogólnego skryptowania i aplikacji, gdzie najwyższe standardy bezpieczeństwa dla losowości nie są wymagane, funkcja `random` w Fish Shell oferuje wygodne i efektywne rozwiązanie.
