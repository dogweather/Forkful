---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:47:04.529122-06:00
description: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E27\u0E48\u0E32\u0E21\u0E35\
  \u0E2D\u0E31\u0E01\u0E02\u0E23\u0E30\u0E01\u0E35\u0E48\u0E15\u0E31\u0E27\u0E2D\u0E22\
  \u0E39\u0E48\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E19\u0E31\u0E49\u0E19 \u0E42\
  \u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\
  \u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\
  \u0E08\u0E2A\u0E2D\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E1B\
  \u0E49\u0E2D\u0E19\u0E40\u0E02\u0E49\u0E32\u0E21\u0E32, \u0E14\u0E33\u0E40\u0E19\
  \u0E34\u0E19\u0E01\u0E32\u0E23\u0E01\u0E31\u0E1A\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\
  \u0E21,\u2026"
lastmod: '2024-03-17T21:57:56.345336-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E27\u0E48\u0E32\u0E21\u0E35\
  \u0E2D\u0E31\u0E01\u0E02\u0E23\u0E30\u0E01\u0E35\u0E48\u0E15\u0E31\u0E27\u0E2D\u0E22\
  \u0E39\u0E48\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E19\u0E31\u0E49\u0E19 \u0E42\
  \u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\
  \u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\
  \u0E08\u0E2A\u0E2D\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E1B\
  \u0E49\u0E2D\u0E19\u0E40\u0E02\u0E49\u0E32\u0E21\u0E32, \u0E14\u0E33\u0E40\u0E19\
  \u0E34\u0E19\u0E01\u0E32\u0E23\u0E01\u0E31\u0E1A\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\
  \u0E21, \u0E2B\u0E23\u0E37\u0E2D\u0E41\u0E04\u0E48\u0E19\u0E31\u0E1A\u0E2D\u0E31\
  \u0E01\u0E02\u0E23\u0E30\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E07\u0E32\u0E19\u0E15\
  \u0E48\u0E32\u0E07\u0E46."
title: "\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\u0E02\
  \u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 7
---

## วิธีทำ:
ใน Lua, คุณสามารถดึงความยาวของสตริงด้วยตัวดำเนินการ `#` ง่ายและรวดเร็ว

```lua
local myString = "Hello, Lua!"
print(#myString)  -- ผลลัพธ์: 11
```

ถ้าสตริงของคุณมีตัวอักขระขึ้นบรรทัดใหม่หรือเป็นสตริงว่างล่ะ?

```lua
local stringWithNewline = "Hello\nLua!"
local emptyString = ""
print(#stringWithNewline)  -- ผลลัพธ์: 10
print(#emptyString)         -- ผลลัพธ์: 0
```

แม้ว่าจะมีตัวอักขระขึ้นบรรทัดใหม่, Lua นับทุกตัวอักขระ และใช่, สตริงที่ว่างมีความยาวเป็น 0

## ลงลึก
ในอดีต, สตริงในบางภาษานั้นยากกว่านี้ คุณอาจจะต้องใช้ฟังก์ชันหรือเมทอดเพื่อหาความยาวของสตริง วันนี้, ใน Lua, มันง่ายดายมากแค่ใช้ตัวดำเนินการ `#`

ทางเลือก? หากคุณกำลังจัดการกับอักขระ Unicode, ตัวดำเนินการ `#` อาจทำคุณเหนื่อยกับอักขระหลายไบต์ ในกรณีนั้น, คุณอาจจะสำรวจไลบรารีเช่น `utf8` Lua เวอร์ชัน 5.3 เป็นต้นไปได้นำเสนอไลบรารีนี้เป็นส่วนหนึ่งของตัวเอง

```lua
local unicodeString = "こんにちは" -- นั่นคือ "Hello" ในภาษาญี่ปุ่น
print(#unicodeString)  -- ผลลัพธ์อาจทำให้คุณแปลกใจถ้าคุณไม่พร้อมสำหรับอักขระหลายไบต์!
print(utf8.len(unicodeString))  -- ผลลัพธ์: 5 ตัวอักขระตามที่คาดหวัง
```

รายละเอียดที่ควรทราบ: Lua ทำให้สตริงเป็น immutable และนำกลับมาใช้ภายในผ่านกลไกที่เรียกว่าการใช้สตริงโดยซ้ำ นี่เป็นเรื่องดีเพราะช่วยประหยัดหน่วยความจำและทำให้การดำเนินการความยาวสตริงเร็วขึ้น

## ดูเพิ่มเติมได้ที่
- Lua 5.4 Reference Manual: การจัดการสตริง – https://www.lua.org/manual/5.4/manual.html#6.4
- ฟังก์ชัน `utf8.len` – ดำดิ่งสู่การจัดการสตริง Unicode อย่างเหมาะสม – https://www.lua.org/manual/5.4/manual.html#pdf-utf8.len
- ประวัติศาสตร์บางอย่างของ Lua และข้อมูลเกี่ยวกับการใช้สตริงโดยซ้ำ – https://www.lua.org/doc/hopl.pdf
