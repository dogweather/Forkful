---
title:                "Створення тимчасового файлу"
html_title:           "C: Створення тимчасового файлу"
simple_title:         "Створення тимчасового файлу"
programming_language: "Kotlin"
category:             "Kotlin"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/kotlin/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## Що це таке і чому?
Створення тимчасового файлу - це процес запису даних в тимчасовий файл на диск, який автоматично видаляється після використання. Програмісти роблять це, щоб зберегти проміжні результати, поївкається з управлінням ресурсами.

## Як це зробити:
У Kotlin створення тимчасових файлів вкрай просте за допомогою бібліотеки `java.io.File`. Ось як це зробити:

```Kotlin
import java.io.File

fun main() {
    val tempFile = File.createTempFile("tempFile", ".txt")
    tempFile.writeText("Hello, Kotlin!")
    println(tempFile.readText())
    tempFile.deleteOnExit()
}
```

Цей код створює тимчасовий файл із ім'ям `tempFile` та розширенням `.txt`, записує у нього текст "Hello, Kotlin!", а потім читає і виводить цей текст. Файл автоматично видалиться після завершення програми.

## Поглиблено:
- **Історичний контекст**: Концепція тимчасових файлів уведена з часом всередину основних операційних систем, де вони широко використовуються для зберігання тимчасових даних.
- **Альтернативи**: Замість створення тимчасового файлу, ми можемо також використовувати in-memory бази даних або кешування, в залежності від задачі.
- **Деталі реалізації**: Коли ви створюєте тимчасовий файл у Kotlin, він створюється в директорії, заданої системною властивістю `java.io.tmpdir`.

## См. також:
- Детальніше про управління файлами в Kotlin: [https://kotlinlang.org/docs/io-files.html](https://kotlinlang.org/docs/io-files.html)
- Створення тимчасових файлів в Java: [https://www.baeldung.com/java-create-temporary-file](https://www.baeldung.com/java-create-temporary-file)
- Введення в обробку файлів Kotlin: [https://www.tutorialkart.com/kotlin-io/file-handling-in-kotlin/](https://www.tutorialkart.com/kotlin-io/file-handling-in-kotlin/)