---
title:                "Зробити першу літеру рядка великою"
html_title:           "Go: Зробити першу літеру рядка великою"
simple_title:         "Зробити першу літеру рядка великою"
programming_language: "Go"
category:             "Go"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/go/capitalizing-a-string.md"
---

{{< edit_this_page >}}

## Що та навіщо?

Перетворення рядка на великі літери - це процес зміни всіх маленьких літер у рядку на великі. Програмісти роблять це для стандартизації даних та кращого порівняння рядків.

## Як зробити:

```Go
package main

import (
	"fmt"
	"strings"
)

func main() {
	my_string := "привіт, світ"
	cap_string := strings.ToUpper(my_string)
	fmt.Println(cap_string)
}
```
При виконанні цього коду виведення буде:

```Go
ПРИВІТ, СВІТ
```

## Поглиблений огляд:

- Історичний контекст: Пригадайте часи машинопису та механічних друкарок, коли велика літера буквально означала натискання клавіші Caps Lock. Та ситуація змінилася. Тепер ми можемо легко маніпулювати рядками за допомогою функцій, таких як ToUpper в Go.

- Альтернативи: Якщо ви хочете змінити першу букву рядка на велику, ви можете використати функцію `Title` в бібліотеці `strings`. 

- Деталі реалізації: Функція `ToUpper` працює, йдучи по всьому вхідному рядку та замінюючи кожну малу літеру відповідною великою літерою.

## Дивись також:

- [Документація Go по бібліотеці `strings`](https://golang.org/pkg/strings/)
- [Введення в Go на офіційному сайті](https://golang.org/doc/intro)
- [Go by Example: String Functions](https://gobyexample.com/string-functions)