---
changelog:
- 2024-01-31, dogweather, reviewed
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:52:06.292195-06:00
description: "Read-Eval-Print Loop (REPL) \u0E40\u0E1B\u0E47\u0E19\u0E2A\u0E20\u0E32\
  \u0E1E\u0E41\u0E27\u0E14\u0E25\u0E49\u0E2D\u0E21\u0E01\u0E32\u0E23\u0E40\u0E02\u0E35\
  \u0E22\u0E19\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E41\u0E1A\u0E1A\u0E07\u0E48\
  \u0E32\u0E22 \u0E46 \u0E41\u0E25\u0E30\u0E42\u0E15\u0E49\u0E15\u0E2D\u0E1A\u0E44\
  \u0E14\u0E49 \u0E0B\u0E36\u0E48\u0E07\u0E23\u0E31\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\
  \u0E25\u0E19\u0E33\u0E40\u0E02\u0E49\u0E32\u0E41\u0E15\u0E48\u0E25\u0E30\u0E23\u0E32\
  \u0E22\u0E01\u0E32\u0E23\u0E08\u0E32\u0E01\u0E1C\u0E39\u0E49\u0E43\u0E0A\u0E49,\
  \ \u0E1B\u0E23\u0E30\u0E40\u0E21\u0E34\u0E19\u0E04\u0E48\u0E32\u0E1E\u0E27\u0E01\
  \u0E19\u0E31\u0E49\u0E19\u2026"
lastmod: '2024-03-17T21:57:56.130608-06:00'
model: gpt-4-0125-preview
summary: "Read-Eval-Print Loop (REPL) \u0E40\u0E1B\u0E47\u0E19\u0E2A\u0E20\u0E32\u0E1E\
  \u0E41\u0E27\u0E14\u0E25\u0E49\u0E2D\u0E21\u0E01\u0E32\u0E23\u0E40\u0E02\u0E35\u0E22\
  \u0E19\u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E41\u0E1A\u0E1A\u0E07\u0E48\u0E32\
  \u0E22 \u0E46 \u0E41\u0E25\u0E30\u0E42\u0E15\u0E49\u0E15\u0E2D\u0E1A\u0E44\u0E14\
  \u0E49 \u0E0B\u0E36\u0E48\u0E07\u0E23\u0E31\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\
  \u0E19\u0E33\u0E40\u0E02\u0E49\u0E32\u0E41\u0E15\u0E48\u0E25\u0E30\u0E23\u0E32\u0E22\
  \u0E01\u0E32\u0E23\u0E08\u0E32\u0E01\u0E1C\u0E39\u0E49\u0E43\u0E0A\u0E49, \u0E1B\
  \u0E23\u0E30\u0E40\u0E21\u0E34\u0E19\u0E04\u0E48\u0E32\u0E1E\u0E27\u0E01\u0E19\u0E31\
  \u0E49\u0E19 \u0E41\u0E25\u0E30\u0E2A\u0E48\u0E07\u0E1C\u0E25\u0E25\u0E31\u0E1E\u0E18\
  \u0E4C\u0E01\u0E25\u0E31\u0E1A\u0E44\u0E1B\u0E22\u0E31\u0E07\u0E1C\u0E39\u0E49\u0E43\
  \u0E0A\u0E49 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\
  \u0E17\u0E35\u0E48\u0E43\u0E0A\u0E49 Elm \u0E43\u0E0A\u0E49 REPL \u0E2A\u0E33\u0E2B\
  \u0E23\u0E31\u0E1A\u0E01\u0E32\u0E23\u0E17\u0E14\u0E25\u0E2D\u0E07\u0E2D\u0E22\u0E48\
  \u0E32\u0E07\u0E23\u0E27\u0E14\u0E40\u0E23\u0E47\u0E27, \u0E01\u0E32\u0E23\u0E41\
  \u0E01\u0E49\u0E44\u0E02\u0E02\u0E49\u0E2D\u0E1C\u0E34\u0E14\u0E1E\u0E25\u0E32\u0E14\
  , \u0E2B\u0E23\u0E37\u0E2D\u0E01\u0E32\u0E23\u0E40\u0E23\u0E35\u0E22\u0E19\u0E23\
  \u0E39\u0E49\u0E20\u0E32\u0E29\u0E32."
title: "\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49 Shell \u0E41\u0E1A\u0E1A\u0E42\u0E15\u0E49\
  \u0E15\u0E2D\u0E1A (REPL)"
weight: 34
---

## วิธีการ:
Elm มาพร้อมกับ REPL ที่ผสานอยู่ในตัว ใช้คำสั่ง `elm repl` จากบรรทัดคำสั่งของคุณเพื่อเริ่มเซสชัน Elm:

```Elm
> import List exposing (..)
> map (\x -> x * 2) [1, 2, 3, 4]
[2,4,6,8] : List number
```

ในเซสชันนี้, หลังจากนำเข้าฟังก์ชั่น List, เราได้คูณตัวเลขในรายการด้วยสองและได้ผลลัพธ์ทันที

คำสั่ง `elm repl --help` แสดงข้อมูลเล็กน้อย:

```
$ elm repl --help
คำสั่ง `repl` เปิดเซสชันการเขียนโปรแกรมแบบโต้ตอบ:

    elm repl

เริ่มต้นศึกษาจาก <https://guide.elm-lang.org> เพื่อเรียนรู้วิธีการใช้งาน! มีตอนหนึ่งที่ใช้ REPL สำหรับทุกอย่าง, ดังนั้นนี่อาจเป็นวิธีที่เร็วที่สุดในการเริ่มต้น

คุณสามารถปรับแต่งคำสั่งนี้ด้วยธงต่อไปนี้:

    --interpreter=<interpreter>
        เส้นทางไปยังตัวแปลภาษา JS ทางเลือก, เช่น node หรือ nodejs

    --no-colors
        ปิดการใช้งานสีใน REPL สิ่งนี้อาจช่วยได้หากคุณกำลังมีปัญหาในการอ่านค่า บางเทอร์มินัลใช้สคีมสีที่กำหนดเองซึ่งแตกต่างอย่างมากจากสี ANSI มาตรฐาน, ดังนั้นเส้นทางอื่นอาจเป็นการเลือกสคีมสีที่มาตรฐานมากขึ้น
```

## การดำดิ่งลึก
REPL ของ Elm อาจดูจำกัดเมื่อเทียบกับภาษาอื่นๆ เช่น Python หรือ JavaScript เนื่องจาก Elm เป็นภาษาที่คอมไพล์ที่มุ่งเน้นไปที่การผลิตแอปพลิเคชันเว็บ ทางประวัติศาสตร์แล้ว Elm มุ่งเน้นไปที่การพัฒนาแอปพลิเคชันเต็มรูปแบบมากกว่าการเขียนสคริปต์หรือการโต้ตอบกับเชลล์

ทางเลือกอื่นๆ ต่อซอฟต์แวร์ REPL ของ Elm รวมถึง `elm-live` และตัวแก้ไขออนไลน์เช่น Ellie ที่คุณสามารถเห็นการเปลี่ยนแปลงของโค้ดได้ในทันทีในเบราว์เซอร์

เกี่ยวกับการใช้งาน, REPL ของ Elm คอมไพล์ส่วนแบ่งของโค้ด Elm เป็น JavaScript ในเบื้องหลัง, ทำให้คุณสามารถรัน Elm ได้อย่างโต้ตอบ นี่คือความแตกต่างจาก REPL ของภาษาที่ตีความ, ซึ่งไม่ต้องการขั้นตอนการคอมไพล์นี้ REPL ของ Elm ยังเป็นรูปแบบที่ง่ายเพื่อให้ภาษาหลักมีน้ำหนักเบาและมุ่งเน้นไปที่เป้าหมาย

## ดูเพิ่มเติม
- คู่มืออย่างเป็นทางการของ Elm: https://guide.elm-lang.org/
- Ellie, สนามเด็กเล่น Elm ออนไลน์: https://ellie-app.com/new
- `elm-live`, เซิร์ฟเวอร์พัฒนาที่ยืดหยุ่นสำหรับ Elm: https://www.elm-live.com/
