---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:46:46.642090-06:00
description: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E19\u0E31\u0E1A\u0E08\u0E33\u0E19\u0E27\u0E19\u0E15\u0E31\
  \u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\
  \u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\
  \u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\u0E1A\u0E02\u0E49\u0E2D\
  \u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E1B\u0E49\u0E2D\u0E19\u0E40\u0E02\u0E49\u0E32\
  \u0E21\u0E32, \u0E27\u0E19\u0E25\u0E39\u0E1B\u0E1C\u0E48\u0E32\u0E19\u0E15\u0E31\
  \u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23,\u2026"
lastmod: '2024-03-17T21:57:56.386720-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\
  \u0E02\u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E19\u0E31\u0E1A\u0E08\u0E33\u0E19\u0E27\u0E19\u0E15\u0E31\
  \u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23 \u0E42\u0E1B\u0E23\u0E41\u0E01\u0E23\u0E21\u0E40\
  \u0E21\u0E2D\u0E23\u0E4C\u0E17\u0E33\u0E40\u0E0A\u0E48\u0E19\u0E19\u0E35\u0E49\u0E40\
  \u0E1E\u0E37\u0E48\u0E2D\u0E15\u0E23\u0E27\u0E08\u0E2A\u0E2D\u0E1A\u0E02\u0E49\u0E2D\
  \u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\u0E1B\u0E49\u0E2D\u0E19\u0E40\u0E02\u0E49\u0E32\
  \u0E21\u0E32, \u0E27\u0E19\u0E25\u0E39\u0E1B\u0E1C\u0E48\u0E32\u0E19\u0E15\u0E31\
  \u0E27\u0E2D\u0E31\u0E01\u0E29\u0E23, \u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E1E\u0E35\
  \u0E22\u0E07\u0E41\u0E04\u0E48\u0E08\u0E31\u0E14\u0E40\u0E23\u0E35\u0E22\u0E07\u0E02\
  \u0E49\u0E2D\u0E21\u0E39\u0E25\u0E43\u0E2B\u0E49\u0E40\u0E23\u0E35\u0E22\u0E1A\u0E23\
  \u0E49\u0E2D\u0E22."
title: "\u0E04\u0E49\u0E19\u0E2B\u0E32\u0E04\u0E27\u0E32\u0E21\u0E22\u0E32\u0E27\u0E02\
  \u0E2D\u0E07\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 7
---

## วิธีทำ:
สัญลักษณ์ `#` ช่วยให้งานเสร็จสิ้นใน bash ใช้มันร่วมกับการขยายพารามิเตอร์ นี่คือวิธีการ:

```bash
my_string="Hello, World!"
string_length=${#my_string}
echo $string_length
```

ตัวอย่างผลลัพธ์:

```
13
```

## ลงลึก
ในอดีต, คนมักใช้ `expr` หรือเครื่องมือภายนอกเช่น `wc -m`, แต่คุณสมบัติในตัวของ Bash ได้เปลี่ยนแปลงเกมส์ ไวยากรณ์ `${#var}` เป็นส่วนหนึ่งของการขยายพารามิเตอร์ที่เ introducedใน Bash มันเร็วและมีประสิทธิภาพเพราะไม่ได้สร้าง subshell หรือเรียกโปรแกรมภายนอก

มีทางเลือกอื่นไหม? แน่นอน, คุณมีเลย:

- `expr length "$my_string"` ให้ผลลัพธ์เดียวกัน, แต่มันค่อนข้างเก่ามาก
- `echo -n $my_string | wc -m` ใช้ `wc` ในการนับ, แต่มันเป็นการทำเกินไปสำหรับงานง่ายๆ

รายละเอียด, รายละเอียด... เมื่อคุณใช้ `${#my_string}`, มันจะให้ความยาวเป็นไบต์โดยค่าเริ่มต้น หากข้อความของคุณอยู่ในด้านยูนิโค้ด, คุณอาจต้องพิจารณาถึงตัวอักษรแบบหลายไบต์ นั่นคือเมื่อสิ่งต่างๆ เริ่มกลายเป็นซับซ้อน

## ดูเพิ่มเติม
ดำดิ่งลงไปในหน้าคู่มือด้วย `man bash` เพื่อเข้าสู่รายละเอียดของการขยายพารามิเตอร์ สำหรับผู้ที่ต้องการจัดการกับสตริงเกินกว่า ASCII พื้นฐาน, คู่มือ Bash-Scripting ขั้นสูงนำเสนอข้อมูลบางอย่าง: https://www.tldp.org/LDP/abs/html/. และเพื่อความรักในการเรียนรู้, ติดตามที่ https://www.gnu.org/software/bash/manual/ เพื่ออัปเดตล่าสุดเกี่ยวกับ Bash.
