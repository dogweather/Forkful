---
title:                "Начало нового проекта"
date:                  2024-01-29T00:02:55.517412-07:00
model:                 gpt-4-0125-preview
simple_title:         "Начало нового проекта"

tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/elixir/starting-a-new-project.md"
changelog:
  - 2024-01-29, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?
Начало нового проекта на Elixir означает создание новой структуры проекта Mix. Программисты делают это, чтобы начать с организованного кода и автоматизированных инструментов, помогающих эффективно строить и тестировать их приложения на Elixir.

## Как:
Чтобы создать новый проект, используйте команду `mix new`:

```elixir
$ mix new my_app
```

Вы увидите что-то вроде этого:

```
* creating README.md
* creating .formatter.exs
* creating .gitignore
* creating mix.exs
* creating lib
* creating lib/my_app.ex
* creating test
* creating test/test_helper.exs
* creating test/my_app_test.exs
```

Перейдите в директорию вашего нового проекта:

```elixir
$ cd my_app
```

Теперь вы можете запустить ваш проект или его тесты:

Запустите ваш проект:

```elixir
$ iex -S mix
```
Протестируйте его:

```elixir
$ mix test
```

## Глубокое Погружение
Инструмент сборки Elixir, Mix, появился из желания предоставить надежный и унифицированный способ создания, настройки и управления проектами. Он был вдохновлен инструментами из других экосистем, такими как Bundler и Rake из Ruby. Mix вносит управление зависимостями и автоматизацию задач в инструментарий Elixir. Его альтернативы в других языках могут быть npm для Node.js или Maven для Java. Однако Mix адаптирован для среды выполнения Elixir и интегрирован с его идиоматическими паттернами. Команда `mix new` создает стандартную структуру с предопределенными директориями и файлами, такими как файлы конфигурации, определения модулей и наборы тестов. Следование конвенциям ключевое в Elixir; это способствует согласованности кода и его читаемости в проектах на Elixir.

## Смотрите Также
- Официальная документация `mix`: [https://hexdocs.pm/mix/Mix.html](https://hexdocs.pm/mix/Mix.html)
- Руководство проекта от Elixir School: [https://elixirschool.com/en/lessons/basics/mix/](https://elixirschool.com/en/lessons/basics/mix/)
