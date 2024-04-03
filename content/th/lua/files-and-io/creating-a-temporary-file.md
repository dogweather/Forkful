---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:15.471820-06:00
description: "\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E40\u0E1B\u0E47\u0E19\u0E01\u0E23\
  \u0E30\u0E1A\u0E27\u0E19\u0E01\u0E32\u0E23\u0E17\u0E33\u0E44\u0E1F\u0E25\u0E4C\u0E17\
  \u0E35\u0E48\u0E21\u0E35\u0E2D\u0E32\u0E22\u0E38\u0E2A\u0E31\u0E49\u0E19\u0E40\u0E1E\
  \u0E37\u0E48\u0E2D\u0E08\u0E31\u0E14\u0E40\u0E01\u0E47\u0E1A\u0E02\u0E49\u0E2D\u0E21\
  \u0E39\u0E25\u0E17\u0E35\u0E48\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E40\u0E09\
  \u0E1E\u0E32\u0E30\u0E43\u0E19\u0E23\u0E30\u0E2B\u0E27\u0E48\u0E32\u0E07\u0E01\u0E32\
  \u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E02\u0E2D\u0E07\u0E42\u0E1B\u0E23\u0E41\u0E01\
  \u0E23\u0E21\u2026"
lastmod: '2024-03-17T21:57:56.373497-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E40\u0E1B\u0E47\u0E19\u0E01\u0E23\
  \u0E30\u0E1A\u0E27\u0E19\u0E01\u0E32\u0E23\u0E17\u0E33\u0E44\u0E1F\u0E25\u0E4C\u0E17\
  \u0E35\u0E48\u0E21\u0E35\u0E2D\u0E32\u0E22\u0E38\u0E2A\u0E31\u0E49\u0E19\u0E40\u0E1E\
  \u0E37\u0E48\u0E2D\u0E08\u0E31\u0E14\u0E40\u0E01\u0E47\u0E1A\u0E02\u0E49\u0E2D\u0E21\
  \u0E39\u0E25\u0E17\u0E35\u0E48\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E40\u0E09\
  \u0E1E\u0E32\u0E30\u0E43\u0E19\u0E23\u0E30\u0E2B\u0E27\u0E48\u0E32\u0E07\u0E01\u0E32\
  \u0E23\u0E17\u0E33\u0E07\u0E32\u0E19\u0E02\u0E2D\u0E07\u0E42\u0E1B\u0E23\u0E41\u0E01\
  \u0E23\u0E21 \u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E2B\u0E25\u0E35\u0E01\u0E40\u0E25\u0E35\
  \u0E48\u0E22\u0E07\u0E44\u0E21\u0E48\u0E43\u0E2B\u0E49\u0E44\u0E1F\u0E25\u0E4C\u0E23\
  \u0E30\u0E1A\u0E1A\u0E40\u0E15\u0E47\u0E21\u0E44\u0E1B\u0E14\u0E49\u0E27\u0E22\u0E02\
  \u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E44\u0E21\u0E48\u0E08\u0E33\u0E40\
  \u0E1B\u0E47\u0E19\u0E41\u0E25\u0E30\u0E08\u0E31\u0E14\u0E01\u0E32\u0E23\u0E01\u0E31\
  \u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E25\u0E31\u0E1A\u0E17\u0E35\u0E48\u0E44\
  \u0E21\u0E48\u0E04\u0E27\u0E23\u0E2D\u0E22\u0E39\u0E48\u0E15\u0E48\u0E2D\u0E44\u0E1B\
  ."
title: "\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\u0E0A\u0E31\u0E48\u0E27\
  \u0E04\u0E23\u0E32\u0E27"
weight: 21
---

## วิธีทำ:
Lua ไม่มีฟังก์ชันในตัวสำหรับไฟล์ชั่วคราว แต่คุณสามารถสร้างโซลูชั่นเองโดยใช้ไลบรารี `os` และ `io`

```Lua
local os = require("os")
local io = require("io")

-- สร้างชื่อไฟล์ชั่วคราวที่ไม่ซ้ำใคร
local function create_temp_filename()
    local temp_file_pattern = 'lua_tempfile_XXXXXX'
    local temp_filename = os.tmpname(temp_file_pattern)
    return temp_filename
end

-- สร้างไฟล์ชั่วคราวใหม่
local temp_filename = create_temp_filename()
local temp_file = io.open(temp_filename, "w")

temp_file:write("ไฟล์นี้เป็นไฟล์ชั่วคราว, มันจะหายไปเร็ว ๆ นี้!")
temp_file:flush()  -- ให้ข้อมูลถูกเขียน
temp_file:close()

-- เพื่อยืนยัน, เรามาตรวจสอบว่าไฟล์มีอยู่จริงและพิมพ์เนื้อหา
local file = io.open(temp_filename, "r")
print(file:read("*a"))  -- ผลลัพธ์: ไฟล์นี้เป็นไฟล์ชั่วคราว, มันจะหายไปเร็ว ๆ นี้!
file:close()

-- ตอนนี้ลบไฟล์เมื่อเสร็จสิ้น
os.remove(temp_filename)
```

## ลงลึกมากขึ้น:
ไฟล์ชั่วคราวเป็นสิ่งจำเป็นในการเขียนโปรแกรมสำหรับการจัดการข้อมูลชั่วคราวตั้งแต่ยุคแรกของการคอมพิวเตอร์สมัยใหม่ พวกมันสำคัญสำหรับการจัดการด้วยข้อมูลที่ไม่จำเป็นต้องมีความถาวรหรือละเอียดอ่อนพอที่จะต้องการการกำจัดทันทีหลังจากใช้งาน

ใน Lua, คุณจะต้องจัดการทำไฟล์ชั่วคราวด้วยตัวเอง เนื่องจากภาษานี้ไม่ได้ให้ไลบรารีมาตรฐานโดยชัดเจนสำหรับเรื่องนี้ ฟังก์ชั่น `os.tmpname` สร้างชื่อไฟล์ที่ไม่ซ้ำใครซึ่งสามารถใช้สำหรับไฟล์ชั่วคราว แต่มันไม่ได้สร้างไฟล์ขึ้นมา งานของคุณคือการสร้าง, จัดการ, และลบมันโดยใช้ไลบรารี `io` สำหรับการดำเนินการไฟล์

ภายใน, `os.tmpname` อาจมีพฤติกรรมที่แตกต่างกันตามวิธีการจัดการไฟล์ชั่วคราวของระบบที่มีอยู่ สำหรับความปลอดภัยยิ่งขึ้น, คุณอาจขยายฟังก์ชัน `create_temp_filename` เพื่อตรวจสอบการมีอยู่ของไฟล์เพื่อหลีกเลี่ยงการชนกันหรือใช้วิธีการที่แข็งแกร่งกว่าข้อกำหนดของระบบ

เป็นข้อควรพิจารณาเพิ่มเติม, เมื่อทำงานกับไฟล์ชั่วคราว, คุณต้องตระหนักถึงความเสี่ยงด้านความปลอดภัย เช่น สภาพแข่งขันหรือช่องโหว่ของการโจมตี symlink บางระบบ ให้แน่ใจว่าไฟล์เหล่านี้ถูกลบหลังจากใช้งาน

## ดูเพิ่มเติมที่:
- คู่มืออ้างอิงของ Lua: https://www.lua.org/manual/5.4/
- ไลบรารี `io`: https://www.lua.org/pil/21.html
- ไลบารี `os`: https://www.lua.org/pil/22.1.html
- คู่มือ OWASP เกี่ยวกับการจัดการไฟล์อย่างปลอดภัย: https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html
