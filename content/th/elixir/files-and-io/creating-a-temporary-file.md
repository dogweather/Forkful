---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 21:45:57.412070-06:00
description: "\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E17\u0E33\u0E44\u0E1F\u0E25\u0E4C\u0E17\u0E35\u0E48\u0E04\
  \u0E38\u0E13\u0E08\u0E30\u0E17\u0E34\u0E49\u0E07\u0E2B\u0E25\u0E31\u0E07\u0E08\u0E32\
  \u0E01\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19\u0E44\u0E1B\u0E44\u0E21\u0E48\u0E19\u0E32\
  \u0E19\u2026"
lastmod: '2024-03-17T21:57:55.872800-06:00'
model: gpt-4-0125-preview
summary: "\u0E01\u0E32\u0E23\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\
  \u0E0A\u0E31\u0E48\u0E27\u0E04\u0E23\u0E32\u0E27\u0E2B\u0E21\u0E32\u0E22\u0E16\u0E36\
  \u0E07\u0E01\u0E32\u0E23\u0E17\u0E33\u0E44\u0E1F\u0E25\u0E4C\u0E17\u0E35\u0E48\u0E04\
  \u0E38\u0E13\u0E08\u0E30\u0E17\u0E34\u0E49\u0E07\u0E2B\u0E25\u0E31\u0E07\u0E08\u0E32\
  \u0E01\u0E43\u0E0A\u0E49\u0E07\u0E32\u0E19\u0E44\u0E1B\u0E44\u0E21\u0E48\u0E19\u0E32\
  \u0E19 \u0E19\u0E31\u0E01\u0E1E\u0E31\u0E12\u0E19\u0E32\u0E17\u0E33\u0E2A\u0E34\u0E48\
  \u0E07\u0E19\u0E35\u0E49\u0E2A\u0E33\u0E2B\u0E23\u0E31\u0E1A\u0E01\u0E32\u0E23\u0E40\
  \u0E01\u0E47\u0E1A\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E0A\u0E31\u0E48\u0E27\u0E04\
  \u0E23\u0E32\u0E27\u0E2B\u0E23\u0E37\u0E2D\u0E40\u0E21\u0E37\u0E48\u0E2D\u0E1E\u0E27\
  \u0E01\u0E40\u0E02\u0E32\u0E15\u0E49\u0E2D\u0E07\u0E01\u0E32\u0E23\u0E2B\u0E25\u0E35\
  \u0E01\u0E40\u0E25\u0E35\u0E48\u0E22\u0E07\u0E01\u0E32\u0E23\u0E2D\u0E38\u0E14\u0E15\
  \u0E31\u0E19\u0E02\u0E2D\u0E07\u0E2E\u0E32\u0E23\u0E4C\u0E14\u0E44\u0E14\u0E23\u0E1F\
  \u0E4C\u0E14\u0E49\u0E27\u0E22\u0E02\u0E49\u0E2D\u0E21\u0E39\u0E25\u0E17\u0E35\u0E48\
  \u0E21\u0E35\u0E2D\u0E32\u0E22\u0E38\u0E01\u0E32\u0E23\u0E43\u0E0A\u0E49\u0E07\u0E32\
  \u0E19\u0E2A\u0E31\u0E49\u0E19\u0E21\u0E32\u0E01."
title: "\u0E2A\u0E23\u0E49\u0E32\u0E07\u0E44\u0E1F\u0E25\u0E4C\u0E0A\u0E31\u0E48\u0E27\
  \u0E04\u0E23\u0E32\u0E27"
weight: 21
---

## วิธีทำ:
ใน Elixir, คุณสามารถสร้างและใช้ไฟล์ชั่วคราวได้ด้วยฟังก์ชัน `System.tmp_dir/1` และโมดูล `File` นี่คือตัวอย่างแบบรวดเร็ว:

```elixir
# ลุยกันเลย!

# หาไดเรกทอรีชั่วคราว
temp_dir = System.tmp_dir!()

# สร้างทางไฟล์ชั่วคราว
temp_file_path = Path.join(temp_dir, "my_temp_file.txt")

# ลองเขียนอะไรซักอย่างแบบชั่วคราว
File.write!(temp_file_path, "สวัสดี, โลกชั่วคราว!")

# อ่านมันสักหน่อย เพื่อให้มั่นใจว่าทุกอย่างโอเค
IO.puts(File.read!(temp_file_path))

# ล้างร่องรอยหลังจากเราและลบไฟล์ชั่วคราว
File.rm!(temp_file_path)
```

ผลลัพธ์ตัวอย่าง:
```
สวัสดี, โลกชั่วคราว!
```

## การลงลึก
ไฟล์ชั่วคราวไม่ได้มีเฉพาะใน Elixir เท่านั้น พวกเขาเป็นสิ่งสำคัญในหลายภาษาการเขียนโปรแกรมเพราะเหมาะสำหรับการจัดการข้อมูลที่สำคัญเฉพาะขณะที่โปรแกรมกำลังทำงาน ก่อนที่พื้นที่เก็บข้อมูลจะราคาถูก การประหยัดพื้นที่ดิสก์เป็นเรื่องสำคัญ - ไฟล์ชั่วคราวช่วยเหลือในเรื่องนั้น ในปัจจุบัน พวกเขามีประโยชน์สำหรับการจัดการทรัพยากรและความปลอดภัย: ข้อมูลที่น้อยถาวรหมายถึงร่องรอยที่น้อยที่จะทิ้งไว้

สำหรับทางเลือกอื่น ใน Elixir, คุณอาจจะทำกลไกไฟล์ชั่วคราวของคุณเองหรือใช้ฟังก์ชัน Erlang โดยตรง (เช่น, `:erlang.mktemp/0`) และสำหรับรายละเอียด เมื่อคุณสร้างไฟล์ชั่วคราว รายละเอียดเช่นการตั้งชื่อจะถูกจัดการโดยระบบปฏิบัติการของคุณ ไม่ใช่ Elixir เอง Elixir เพียงขอให้ระบบปฏิบัติการบอกว่าจะเก็บไฟล์นั้นไว้ชั่วคราวที่ไหน และระบบปฏิบัติการก็ตอบกลับ

## ดูเพิ่มเติม
สำหรับการจัดการไฟล์ของ Elixir เพิ่มเติม:
- โมดูล `File` ของ Elixir: https://hexdocs.pm/elixir/File.html
- เอกสารทางการสำหรับ `System.tmp_dir/1`: https://hexdocs.pm/elixir/System.html#tmp_dir/1

การสำรวจความสามารถในการจัดการไฟล์ของ Erlang:
- โมดูล `file` ของ Erlang: http://erlang.org/doc/man/file.html
