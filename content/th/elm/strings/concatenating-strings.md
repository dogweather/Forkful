---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:45:15.533901-06:00
description: "\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\
  \u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E19\u0E33\u0E2A\u0E2D\u0E07\
  \u0E2B\u0E23\u0E37\u0E2D\u0E21\u0E32\u0E01\u0E01\u0E27\u0E48\u0E32\u0E19\u0E31\u0E49\
  \u0E19\u0E02\u0E2D\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E21\u0E32\u0E15\
  \u0E34\u0E14\u0E01\u0E31\u0E19 \u0E40\u0E1B\u0E23\u0E35\u0E22\u0E1A\u0E40\u0E2A\u0E21\
  \u0E37\u0E2D\u0E19\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E40\u0E17\u0E1B\u0E01\u0E32\
  \u0E27 \u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\u0E38\u0E13\u0E2A\u0E32\u0E21\
  \u0E32\u0E23\u0E16\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E43\
  \u0E2B\u0E21\u0E48\u0E44\u0E14\u0E49\u0E17\u0E31\u0E19\u0E17\u0E35\u0E40\u0E1E\u0E37\
  \u0E48\u0E2D\u0E41\u0E2A\u0E14\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21,\
  \ \u0E2A\u0E23\u0E49\u0E32\u0E07\u0E40\u0E17\u0E21\u0E40\u0E1E\u0E25\u0E15\u2026"
lastmod: '2024-03-17T21:57:56.120479-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\
  \u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\u0E01\u0E32\u0E23\u0E19\u0E33\u0E2A\u0E2D\u0E07\
  \u0E2B\u0E23\u0E37\u0E2D\u0E21\u0E32\u0E01\u0E01\u0E27\u0E48\u0E32\u0E19\u0E31\u0E49\
  \u0E19\u0E02\u0E2D\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E21\u0E32\u0E15\
  \u0E34\u0E14\u0E01\u0E31\u0E19 \u0E40\u0E1B\u0E23\u0E35\u0E22\u0E1A\u0E40\u0E2A\u0E21\
  \u0E37\u0E2D\u0E19\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E40\u0E17\u0E1B\u0E01\u0E32\
  \u0E27 \u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\u0E38\u0E13\u0E2A\u0E32\u0E21\
  \u0E32\u0E23\u0E16\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E43\
  \u0E2B\u0E21\u0E48\u0E44\u0E14\u0E49\u0E17\u0E31\u0E19\u0E17\u0E35\u0E40\u0E1E\u0E37\
  \u0E48\u0E2D\u0E41\u0E2A\u0E14\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21,\
  \ \u0E2A\u0E23\u0E49\u0E32\u0E07\u0E40\u0E17\u0E21\u0E40\u0E1E\u0E25\u0E15 \u0E41\
  \u0E25\u0E30\u0E2D\u0E35\u0E01\u0E21\u0E32\u0E01\u0E21\u0E32\u0E22."
title: "\u0E01\u0E32\u0E23\u0E15\u0E48\u0E2D\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 3
---

## วิธีการ:
Elm มีโอเปอเรเตอร์ที่เรียบร้อย `(++)` มาช่วยให้การเชื่อมสตริงเป็นเรื่องง่าย:

```Elm
greeting : String
greeting =
    "Hello, " ++ "world!"

-- "Hello, world!"
```

แต่บางครั้งคุณอาจมีชิ้นส่วนเยอะๆ อย่ากลัว, `++` สามารถเชื่อมต่อกันได้:

```Elm
fullName : String
fullName =
    "Elm" ++ " " ++ "Lang"

-- "Elm Lang"
```

และสำหรับรายการของสตริง, `String.join` เป็นเพื่อนของคุณ:

```Elm
words : List String
words =
    ["Join", "the", "Elm", "club"]

sentence : String
sentence =
    String.join " " words

-- "Join the Elm club"
```

## ลึกซึ้ง
ในอดีต, คุณมักจะต่อสตริงด้วยฟังก์ชันที่ซับซ้อนในภาษาอื่นๆ ใน Elm, มันเคยเป็นเรื่องง่ายเสมอด้วยโอเปอเรเตอร์ `(++)` หากคุณต่อสตริงเป็นจำนวนมาก ประสิทธิภาพอาจเข้ามาเกี่ยวข้อง; การใช้ `(++)` กับสตริงยาวอาจจะช้าลงเนื่องจาก Elm ต้องเดินผ่านสตริงทางซ้ายของ `(++)` ทุกครั้ง

ยังมี "การแทรกตัวแปร" ในบางภาษา, แต่ Elm ไม่ทำการแทรกตัวแปรแบบสตริง ไม่ต้องกังวล, `(++)` และ `String.join` ช่วยคุบคลุมเราได้

ใต้ฝาปิด, เมื่อ Elm ทำการต่อสตริง, มันพยายามทำให้ฉลาดเกี่ยวกับมัน, บ่อยครั้งโดยใช้การดำเนินการที่เหมาะสมของ JavaScript, ซึ่งเป็นภาษาที่ Elm จะคอมไพล์ลงไปในที่สุด ดังนั้นแม้ว่า `(++)` อาจดูเรียบง่าย, แต่มีความฉลาดบางอย่างกำลังเกิดขึ้นเบื้องหลังเพื่อให้ทุกอย่างทำงานได้อย่างรวดเร็ว

## ดูเพิ่มเติม
- เอกสารการใช้งานอย่างเป็นทางการของ Elm เกี่ยวกับสตริง: https://package.elm-lang.org/packages/elm/core/latest/String
- คู่มือ Elm, ที่คุณสามารถเรียนรู้เพิ่มเติมเกี่ยวกับสตริง: https://guide.elm-lang.org/strings/
