---
title:                "Робота з YAML"
aliases:
- uk/elm/working-with-yaml.md
date:                  2024-02-03T19:25:39.063149-07:00
model:                 gpt-4-0125-preview
simple_title:         "Робота з YAML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/elm/working-with-yaml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Що і чому?
Elm не має вбудованої підтримки для YAML, формату серіалізації даних, який часто використовується для файлів конфігурації або обміну даними, через його сильний акцент на типовій безпеці та передбачуваних результатах. Однак, програмісти часто зустрічаються з YAML при роботі з API або конфігураціями в веб-розробці, що потребує надійних методів для аналізу даних YAML в строго типізовану екосистему Elm для безперебійної інтеграції та маніпуляції.

## Як це зробити:
Щоб працювати з YAML в Elm, вам зазвичай потрібно перетворити YAML на JSON поза Elm, а потім використовувати вбудовані функції декодера JSON Elm для роботи з даними. Хоча цей підхід вимагає додаткового кроку конвертації, він використовує сильну систему типів Elm для забезпечення цілісності даних. Популярні інструменти для конвертації YAML в JSON включають онлайн-конвертери або сервіси на сервері. Після отримання JSON ви можете використовувати модуль `Json.Decode` Elm для роботи з даними.

Спочатку, припустимо, у вас є наступні дані YAML:

```yaml
person:
  name: Jane Doe
  age: 30
```

Перетворіть їх на формат JSON:

```json
{
  "person": {
    "name": "Jane Doe",
    "age": 30
  }
}
```

Потім визначте вашу модель Elm та декодер:

```elm
module Main exposing (..)

import Html exposing (text)
import Json.Decode as Decode

type alias Person =
    { name : String
    , age : Int
    }

personDecoder : Decode.Decoder Person
personDecoder =
    Decode.map2 Person
        (Decode.field "name" Decode.string)
        (Decode.field "age" Decode.int)

```

Щоб використати цей декодер для конвертації JSON у тип Elm:

```elm
import Json.Decode as Decode

jsonString = 
    """
    {
      "person": {
        "name": "Jane Doe",
        "age": 30
      }
    }
    """

decodeResult = Decode.decodeString (Decode.field "person" personDecoder) jsonString

main =
    case decodeResult of
        Ok person ->
            Html.text ("Привіт, " ++ person.name ++ "!")
            
        Err _ ->
            Html.text "Під час декодування сталася помилка."
```

Вивід (відображено в додатку Elm):
```
Привіт, Jane Doe!
```

Цей підхід забезпечує можливість працювати з даними YAML в Elm, використовуючи JSON як проміжний формат, і використовувати міцну систему типів та можливості декодування JSON Elm для безпечної та ефективної маніпуляції з зовнішніми даними.
