---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:49:08.702061-06:00
description: "\u0E01\u0E32\u0E23\u0E1E\u0E34\u0E21\u0E1E\u0E4C\u0E02\u0E49\u0E2D\u0E21\
  \u0E39\u0E25\u0E14\u0E35\u0E1A\u0E31\u0E01\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\
  \ \u0E01\u0E32\u0E23\u0E1B\u0E25\u0E48\u0E2D\u0E22\u0E02\u0E49\u0E2D\u0E21\u0E39\
  \u0E25\u0E40\u0E1E\u0E34\u0E48\u0E21\u0E40\u0E15\u0E34\u0E21\u0E2D\u0E2D\u0E01\u0E21\
  \u0E32\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\
  \u0E38\u0E13\u0E40\u0E02\u0E49\u0E32\u0E43\u0E08\u0E27\u0E48\u0E32\u0E42\u0E04\u0E49\
  \u0E14\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\u0E01\u0E33\u0E25\u0E31\u0E07\u0E17\u0E33\
  \u0E2D\u0E30\u0E44\u0E23\u0E2D\u0E22\u0E39\u0E48\u2026"
lastmod: '2024-03-17T21:57:56.647905-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E1E\u0E34\u0E21\u0E1E\u0E4C\u0E02\u0E49\u0E2D\u0E21\
  \u0E39\u0E25\u0E14\u0E35\u0E1A\u0E31\u0E01\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\u0E07\
  \ \u0E01\u0E32\u0E23\u0E1B\u0E25\u0E48\u0E2D\u0E22\u0E02\u0E49\u0E2D\u0E21\u0E39\
  \u0E25\u0E40\u0E1E\u0E34\u0E48\u0E21\u0E40\u0E15\u0E34\u0E21\u0E2D\u0E2D\u0E01\u0E21\
  \u0E32\u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\u0E49\u0E04\
  \u0E38\u0E13\u0E40\u0E02\u0E49\u0E32\u0E43\u0E08\u0E27\u0E48\u0E32\u0E42\u0E04\u0E49\
  \u0E14\u0E02\u0E2D\u0E07\u0E04\u0E38\u0E13\u0E01\u0E33\u0E25\u0E31\u0E07\u0E17\u0E33\
  \u0E2D\u0E30\u0E44\u0E23\u0E2D\u0E22\u0E39\u0E48 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\
  \u0E21\u0E40\u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E41\u0E1A\u0E1A\u0E19\u0E35\u0E49\
  \u0E40\u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E08\u0E31\u0E1A\u0E41\u0E25\
  \u0E30\u0E41\u0E01\u0E49\u0E44\u0E02\u0E1A\u0E31\u0E04\u0E44\u0E14\u0E49\u0E07\u0E48\
  \u0E32\u0E22\u0E02\u0E36\u0E49\u0E19."
title: "\u0E01\u0E32\u0E23\u0E1E\u0E34\u0E21\u0E1E\u0E4C\u0E1C\u0E25\u0E25\u0E31\u0E1E\
  \u0E18\u0E4C\u0E01\u0E32\u0E23\u0E41\u0E01\u0E49\u0E44\u0E02\u0E42\u0E04\u0E49\u0E14"
weight: 33
---

## วิธีการ:
คุ้นเคยกับ `echo` - มีดสวิสสำหรับการแสดงผลใน Fish นี่คือวิธีการเพิ่มการพิมพ์ดีบักเข้าไปในสคริปต์เชลล์ของคุณ

```Fish Shell
function greet
    set name $argv[1]
    echo "เฮ้, $name! มาดีบักกันเถอะ."
    echo "กำลังรันฟังก์ชัน greet" >&2
end

greet "Ada"
```
ตัวอย่างผลลัพธ์:
```
เฮ้, Ada! มาดีบักกันเถอะ.
กำลังรันฟังก์ชัน greet
```
Standard out (`stdout`) นั้นเป็นเวทีหลักของสคริปต์ของคุณ แต่สำหรับการพูดคุยดีบัก ให้ใช้ standard error (`stderr`) ด้วย `>&2`

## การดำดิ่งลึก
ย้อนกลับไปตอนที่จอภาพมีความลึกเท่ากับความกว้าง การแสดงผลถือเป็นสิ่งที่มีค่า  Standard out (`stdout`) จึงเป็นช่องทางแสดงผลที่สะอาดสำหรับผู้ใช้ ขณะที่ standard error (`stderr`) กลายเป็นช่องทางหลังบ้านสำหรับการสนทนาของโปรแกรมเมอร์เท่านั้น เช่น ข้อมูลดีบัก

ใน Fish, คำสั่งมาตรฐานสำหรับการแสดงผลคือ `echo`, `printf`, และ `print` คำสั่ง `echo` เข้าใจง่ายและโดยส่วนใหญ่ใช้สำหรับข้อความง่ายๆ และการดีบักแบบแทรก

คุณไม่ได้ถูกจำกัดเพียงแค่ `echo` เท่านั้น ถ้าชอบ `printf` สำหรับสตริงที่มีการจัดรูปแบบ หรือใช้การเปลี่ยนทิศทาง (`>` หรือ `>>`) เพื่อทิ้งข้อมูลดีบักเข้าไปในไฟล์เพื่อตรวจสอบในภายหลัง

สำหรับการประยุกต์ใช้งาน เรื่องที่ใช้ `stderr` สำหรับข้อมูลดีบักเป็นข้อตกลงจากโลก Unix ช่วยให้สามารถแยกข้อมูลจริง (actual output) ออกจากเสียงรบกวนดีบัก (debug noise) นั่นหมายความว่าผู้ใช้ยังสามารถทำการ pipe ผลลัพธ์จริงของสคริปต์ได้อย่างมีประสิทธิภาพโดยไม่ต้องกังวลเกี่ยวกับข้อมูลดีบักที่รบกวน

## ดูเพิ่มเติม
- คู่มือเชลล์ Fish เกี่ยวกับ [คำสั่ง](https://fishshell.com/docs/current/commands.html)
- StackOverflow: การสนทนาและตัวอย่างสำหรับ [การดีบักใน Fish](https://stackoverflow.com/questions/tagged/fish)
- Greg's Wiki: ข้อมูลลึกเกี่ยวกับ [การเปลี่ยนทาง I/O](https://mywiki.wooledge.org/BashGuide/InputAndOutput#Redirection)
