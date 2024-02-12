---
title:                "Поиск длины строки"
date:                  2024-01-28T23:58:25.537266-07:00
model:                 gpt-4-0125-preview
simple_title:         "Поиск длины строки"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/c-sharp/finding-the-length-of-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?

Нахождение длины строки означает подсчет ее символов. Мы делаем это для валидации ввода, итерации по символам, выделения ресурсов или просто из любопытства – знать размер важно.

## Как это сделать:

В C# свойство `string.Length` дает вам количество символов в строке. Вот как его использовать:

```C#
using System;

class Program
{
    static void Main()
    {
        string example = "Привет, мир!";
        Console.WriteLine(example.Length); // Вывод: 13
    }
}
```

Легко, правда? Но помните, оно считает *символы*, а не байты. С эмодзи или специальными символами все может стать сложнее. Об этом позже.

## Подробнее

Исторически, нахождение длины строки было связано с управлением и манипуляцией памятью в программировании. Поскольку C# является языком высокого уровня, он абстрагирует эту низкоуровневую работу. Тем не менее, хорошо знать, что находится под капотом.

Альтернативы? Конечно! Вы можете встретить `example.ToCharArray().Length` на практике, но это просто лишняя работа для получения того же результата.

Теперь о тех сложных символах. Свойство `Length` в C# подсчитывает объекты `char` строки, каждый из которых представляет собой единицу кода UTF-16. Это нормально, пока вы не столкнетесь с *суррогатными парами* – символами вроде эмодзи, которым нужны два объекта `char`. Вот в чем дело: `Length` считает их за два. Да.

Для точного подсчета *визуальных* символов или *кластеров графем* вам понадобится класс `StringInfo` из `System.Globalization`:

```C#
using System;
using System.Globalization;

class Program
{
    static void Main()
    {
        string example = "👍"; // Эмодзи в виде пальца вверх

        Console.WriteLine(example.Length); // Вывод: 2 <- Из-за суррогатной пары!
        Console.WriteLine(new StringInfo(example).LengthInTextElements); // Вывод: 1
    }
}
```

Понимаете разницу? Это не просто академический интерес; это может значительно повлиять на обработку текста.

## Смотрите также

Изучите больше с этими ресурсами:

- [Официальная документация Microsoft по строкам](https://docs.microsoft.com/ru-ru/dotnet/csharp/programming-guide/strings/)
- [Понимание Unicode и UTF-16](https://unicodebook.readthedocs.io/unicode_encodings.html)
- [Документация по классу StringInfo](https://docs.microsoft.com/ru-ru/dotnet/api/system.globalization.stringinfo?view=net-6.0)

Знайте свои строки, обращайтесь с ними мудро и пишите код, который считается – во всех смыслах.
