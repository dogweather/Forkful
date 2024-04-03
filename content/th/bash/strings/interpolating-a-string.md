---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:47:38.101112-06:00
description: "\u0E01\u0E32\u0E23\u0E43\u0E2A\u0E48\u0E04\u0E48\u0E32\u0E43\u0E19\u0E2A\
  \u0E15\u0E23\u0E34\u0E07 (String interpolation) \u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\
  \u0E49\u0E04\u0E38\u0E13\u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E41\u0E17\u0E23\u0E01\
  \u0E04\u0E48\u0E32\u0E25\u0E07\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E44\u0E14\
  \u0E49 \u0E21\u0E31\u0E19\u0E40\u0E1B\u0E47\u0E19\u0E40\u0E04\u0E23\u0E37\u0E48\u0E2D\
  \u0E07\u0E21\u0E37\u0E2D\u0E17\u0E35\u0E48\u0E21\u0E35\u0E1B\u0E23\u0E30\u0E42\u0E22\
  \u0E0A\u0E19\u0E4C\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E01\u0E32\u0E23\u0E2A\u0E23\
  \u0E49\u0E32\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E41\u0E1A\u0E1A\u0E01\
  \u0E33\u0E2B\u0E19\u0E14\u0E40\u0E2D\u0E07,\u2026"
lastmod: '2024-03-17T21:57:56.382066-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E43\u0E2A\u0E48\u0E04\u0E48\u0E32\u0E43\u0E19\u0E2A\
  \u0E15\u0E23\u0E34\u0E07 (String interpolation) \u0E0A\u0E48\u0E27\u0E22\u0E43\u0E2B\
  \u0E49\u0E04\u0E38\u0E13\u0E2A\u0E32\u0E21\u0E32\u0E23\u0E16\u0E41\u0E17\u0E23\u0E01\
  \u0E04\u0E48\u0E32\u0E25\u0E07\u0E43\u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07\u0E44\u0E14\
  \u0E49 \u0E21\u0E31\u0E19\u0E40\u0E1B\u0E47\u0E19\u0E40\u0E04\u0E23\u0E37\u0E48\u0E2D\
  \u0E07\u0E21\u0E37\u0E2D\u0E17\u0E35\u0E48\u0E21\u0E35\u0E1B\u0E23\u0E30\u0E42\u0E22\
  \u0E0A\u0E19\u0E4C\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E01\u0E32\u0E23\u0E2A\u0E23\
  \u0E49\u0E32\u0E07\u0E02\u0E49\u0E2D\u0E04\u0E27\u0E32\u0E21\u0E41\u0E1A\u0E1A\u0E01\
  \u0E33\u0E2B\u0E19\u0E14\u0E40\u0E2D\u0E07, \u0E01\u0E32\u0E23\u0E17\u0E33\u0E04\
  \u0E33\u0E2A\u0E31\u0E48\u0E07\u0E2D\u0E31\u0E15\u0E42\u0E19\u0E21\u0E31\u0E15\u0E34\
  , \u0E41\u0E25\u0E30\u0E01\u0E32\u0E23\u0E40\u0E02\u0E35\u0E22\u0E19\u0E2A\u0E04\
  \u0E23\u0E34\u0E1B\u0E15\u0E4C\u0E2D\u0E22\u0E48\u0E32\u0E07\u0E40\u0E08\u0E4B\u0E07\
  ."
title: "\u0E01\u0E32\u0E23\u0E41\u0E17\u0E23\u0E01\u0E04\u0E48\u0E32\u0E25\u0E07\u0E43\
  \u0E19\u0E2A\u0E15\u0E23\u0E34\u0E07"
weight: 8
---

## วิธีทำ:
สตริงใน Bash ทำงานร่วมกับตัวแปรได้ดี ใส่ตัวแปรลงไปในสตริงพร้อมกับเครื่องหมายปีกกาบางๆ และคุณก็ทำได้สำเร็จ

```Bash
name="World"
greeting="สวัสดี, ${name}!"
echo $greeting
```

ผลลัพธ์:
```
สวัสดี, โลก!
```

Bash บอกว่า, "ให้มันยืดหยุ่น" เปลี่ยน `name`, แล้วคำทักทายของคุณก็จะเปลี่ยนตาม

```Bash
name="ขาใหญ่ Bash"
greeting="สวัสดี, ${name}!"
echo $greeting
```

ผลลัพธ์:
```
สวัสดี, ขาใหญ่ Bash!
```

## ลงลึก
ในอดีต, โปรแกรมเมอร์ต่อสตริงกันด้วยการต่อข้อความ มันกลายเป็นเรื่องรก การใส่ค่าในสตริงเข้ามาเหมือนฮีโร่เพื่อรหัสที่สะอาดและง่ายต่อการอ่านมากขึ้น

Bash, ไม่เหมือนกับภาษาอื่นๆ ไม่ต้องจุกจิก—แค่สัญลักษณ์ดอลลาร์และปีกกาบางๆ ภาษาอื่นๆ อาจมีไวยากรณ์พิเศษหรือฟังก์ชัน ใน Bash, มันเกี่ยวกับปีกกาและตัวอักษรหนีได้บ้างหากคุณต้องการความหรูหรา

ตัวเลือกอื่นๆ? แน่นอน, คุณสามารถต่อข้อความหรือใช้ `echo` โดยไม่มีปีกกาหากคุณไม่ทำอะไรซับซ้อน แต่ทำไมต้องยอมรับ?

สำหรับการดำเนินการ, เมื่อ Bash เห็น `${}`, มันจะคว้าค่าของตัวแปรและสลับมันเข้าไป, ไม่มีคำถาม นี้ทำให้แน่ใจว่าสิ่งที่คุณเห็น (ในโค้ดของคุณ) คือสิ่งที่คุณได้รับ (ในผลลัพธ์ของคุณ)

## ดูเพิ่มเติม
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับเวทย์มนตร์สตริง:

- การจัดการสตริง Bash: https://www.gnu.org/software/bash/manual/html_node/Shell-Parameter-Expansion.html
- คู่มือการเขียนสคริปต์ Bash ระดับสูง: https://tldp.org/LDP/abs/html/
- Stack Overflow (ตัวอย่างการใช้งานจริงสำหรับปัญหาในโลกแห่งความจริง): https://stackoverflow.com/questions/tagged/bash
