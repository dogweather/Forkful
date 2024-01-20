---
title:                "Створення тимчасового файлу"
html_title:           "C: Створення тимчасового файлу"
simple_title:         "Створення тимчасового файлу"
programming_language: "Go"
category:             "Go"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/go/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## Що & Навіщо?

Створення тимчасового файлу - це процес запису даних в проміжний файл, який видаляється після зчитування. Програмісти роблять це для ефективного міжпроцесного обміну даними без навантаження на основну пам'ять комп'ютера.

## Як це робиться:

```Go
package main

import (
    "fmt"
    "io/ioutil"
    "log"
)

func main() {
    tempFile, err := ioutil.TempFile("", "sample")
    if err != nil {
        log.Fatal(err)
    }
    defer tempFile.Close()

    tempFile.WriteString("Привіт світ!\n")
    fmt.Println("Ім'я тимчасового файлу:", tempFile.Name())
}
```
Приклад виведе назву тимчасового файлу, в якому зберігається текст "Привіт світ!".

## Поглиблений розбір:

1. Основна ідея створення тимчасового файлу в Go виникла у 2007 році в Unix системах, де було принято використовувати /tmp для тимчасових файлів.
2. Альтернатива - створення довгострокових файлів, які не видаляються автоматично, але це може привести до небажаного накопичення даних. Також можна використовувати вбудовану пам'ять, але це обмежує кількість даних, які можна обробити.
3. В Go тимчасовий файл створюється за допомогою ioutil.TempFile. Вона створює унікальний файл і відкриває його для запису. Файлу присвоюється випадкове ім'я з префіксом, який ви вказали.

## Дивись також:

1. [Документація Go для ioutil.TempFile](https://golang.org/pkg/io/ioutil/#TempFile)
2. [Створення та робота з файлами Go](https://www.devdungeon.com/content/working-files-go)
3. [Tutorial: How to create, open, read, write, and delete a file in Go](https://dev.to/sagar/how-to-create-open-read-write-and-delete-a-file-in-go-3cl3)