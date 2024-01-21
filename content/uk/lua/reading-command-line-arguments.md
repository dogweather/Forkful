---
title:                "Читання аргументів командного рядка"
date:                  2024-01-20T17:56:48.117139-07:00
model:                 gpt-4-1106-preview
simple_title:         "Читання аргументів командного рядка"
programming_language: "Lua"
category:             "Lua"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/lua/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## Що & Навіщо?
Читання аргументів командного рядка дозволяє вашій програмі отримувати дані ще до її старту. Програмісти це роблять, аби управляти поведінкою програми без змін коду.

## Як це робити:
```Lua
-- Вивести всі аргументи командного рядка
for i = 1, #arg do
  print(i, arg[i])
end

-- запустити програму з аргументами:
-- lua yourscript.lua любовь спокій воля
-- Вивід:
-- 1	любовь
-- 2	спокій
-- 3	воля
```

## Поглиблений Розбір
В історії, Lua (від Португальського "Місяць") з'явилась у 1993 і з того часу аргументи командного рядка були ключем до гнучкості скриптів. Є альтернативи, наприклад, використання конфігураційних файлів або змінних оточення, але аргументи прості у використанні і розповсюджені. Коли обробляєте `arg`, перший аргумент, `arg[0]`, це зазвичай шлях до сценарію, а індексація починається з `arg[1]`. Ви можете перевірити #arg для кількості аргументів.

## Дивись Також
- [Programming in Lua (Fourth edition)](https://www.lua.org/pil/contents.html)
- [Lua 5.4 Reference Manual](https://www.lua.org/manual/5.4/)
- [Lua Users Wiki - Command Line Arguments](http://lua-users.org/wiki/CommandLineArguments)